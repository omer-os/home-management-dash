<script lang="ts">
  import type { Snippet } from "svelte";

  let {
    progress = $bindable(0.3),
    full = false,
    draggable = false,
    size = 200,
    strokeWidth = 10,
    children,
  }: {
    progress?: number;
    full?: boolean;
    draggable?: boolean;
    size?: number;
    strokeWidth?: number;
    children?: Snippet;
  } = $props();

  let svgEl: SVGSVGElement | undefined = $state();
  let dragging = $state(false);

  const radius = (size - strokeWidth) / 2;
  const cx = size / 2;
  const cy = size / 2;

  let startAngle = $derived(full ? 0 : 135);
  let endAngle = $derived(full ? 359.99 : 405);
  let totalAngle = $derived(endAngle - startAngle);
  let valueAngle = $derived(
    startAngle + Math.min(progress, 0.999) * totalAngle,
  );

  function polarToCartesian(angle: number) {
    const rad = ((angle - 90) * Math.PI) / 180;
    return {
      x: cx + radius * Math.cos(rad),
      y: cy + radius * Math.sin(rad),
    };
  }

  function describeArc(start: number, end: number) {
    const diff = end - start;
    if (diff >= 359.99) {
      const mid = polarToCartesian(start + 180);
      const s = polarToCartesian(start);
      return `M ${s.x} ${s.y} A ${radius} ${radius} 0 1 1 ${mid.x} ${mid.y} A ${radius} ${radius} 0 1 1 ${s.x} ${s.y}`;
    }
    const s = polarToCartesian(start);
    const e = polarToCartesian(end);
    const largeArc = diff > 180 ? 1 : 0;
    return `M ${s.x} ${s.y} A ${radius} ${radius} 0 ${largeArc} 1 ${e.x} ${e.y}`;
  }

  function angleFromEvent(e: MouseEvent | TouchEvent) {
    if (!svgEl) return;
    const rect = svgEl.getBoundingClientRect();
    const scaleX = size / rect.width;
    const scaleY = size / rect.height;
    const clientX = "touches" in e ? e.touches[0].clientX : e.clientX;
    const clientY = "touches" in e ? e.touches[0].clientY : e.clientY;
    const x = (clientX - rect.left) * scaleX - cx;
    const y = (clientY - rect.top) * scaleY - cy;
    let angle = (Math.atan2(y, x) * 180) / Math.PI + 90;
    if (angle < 0) angle += 360;
    if (!full) {
      if (angle < startAngle && angle < 90) angle += 360;
      if (angle < startAngle || angle > endAngle) return;
    }
    progress = Math.max(0, Math.min(1, (angle - startAngle) / totalAngle));
  }

  function onPointerDown(e: MouseEvent | TouchEvent) {
    if (!draggable) return;
    e.preventDefault();
    dragging = true;
    window.addEventListener("mousemove", onPointerMove);
    window.addEventListener("mouseup", onPointerUp);
    window.addEventListener("touchmove", onPointerMove, { passive: false });
    window.addEventListener("touchend", onPointerUp);
  }

  function onPointerMove(e: MouseEvent | TouchEvent) {
    if (!dragging) return;
    e.preventDefault();
    angleFromEvent(e);
  }

  function onPointerUp() {
    dragging = false;
    window.removeEventListener("mousemove", onPointerMove);
    window.removeEventListener("mouseup", onPointerUp);
    window.removeEventListener("touchmove", onPointerMove);
    window.removeEventListener("touchend", onPointerUp);
  }

  let bgPath = $derived(describeArc(startAngle, endAngle));
  let valuePath = $derived(describeArc(startAngle, valueAngle));
  let thumbPos = $derived(polarToCartesian(valueAngle));
</script>

<div class="relative" style="width: {size}px; height: {size}px;">
  <svg
    bind:this={svgEl}
    viewBox="0 0 {size} {size}"
    class="w-full h-full"
    role={draggable ? "slider" : undefined}
    aria-valuenow={draggable ? progress : undefined}
  >
    <defs>
      <linearGradient id="arcGradient" x1="0%" y1="0%" x2="100%" y2="100%">
        <stop offset="0%" stop-color="oklch(0.8 0.18 90)" />
        <stop offset="100%" stop-color="oklch(0.6 0.2 40)" />
      </linearGradient>
    </defs>
    <path
      d={bgPath}
      fill="none"
      stroke="oklch(0.25 0 0)"
      stroke-width={strokeWidth}
      stroke-linecap="round"
    />
    {#if progress > 0}
      <path
        d={valuePath}
        fill="none"
        stroke="url(#arcGradient)"
        stroke-width={strokeWidth}
        stroke-linecap="round"
      />
    {/if}
    {#if draggable}
      <circle
        cx={thumbPos.x}
        cy={thumbPos.y}
        r={strokeWidth * 2}
        fill="transparent"
        class="cursor-grab"
        class:cursor-grabbing={dragging}
        onmousedown={onPointerDown}
        ontouchstart={onPointerDown}
      />
      <circle
        cx={thumbPos.x}
        cy={thumbPos.y}
        r={strokeWidth * 0.8}
        fill="white"
        class="pointer-events-none drop-shadow-md"
      />
    {/if}
  </svg>
  <div
    class="absolute inset-0 flex items-center justify-center pointer-events-none"
  >
    {#if children}
      {@render children()}
    {/if}
  </div>
</div>

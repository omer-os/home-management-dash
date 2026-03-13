<script>
  import { Sun, Plus, Minus, Type, Sparkles, CloudSun } from "@lucide/svelte";
  import Card from "../ui/card/card.svelte";
  import Button from "../ui/button/button.svelte";
  import CirclarSlider from "../ui/CirclarSlider.svelte";
  let brightness = $state(0.8);
</script>

<Card class="py-0 gap-0  flex-1 flex flex-col overflow-hidden relative">
  <div class="flex gap-2 p-4 pb-2 items-center">
    <div
      class="rounded-full flex items-center justify-center h-12 w-12 bg-secondary"
    >
      <Sun class="fill-foreground" />
    </div>
    <p class="font-medium text-lg">Smart Lighting</p>
  </div>

  <div class="flex gap-3 overflow-x-auto pb-3 px-4">
    <Button class="text-xs" variant="secondary" size="sm">8 watt</Button>
    <Button class="text-xs" variant="secondary" size="sm">9 watt</Button>
    <Button class="text-xs" variant="default" size="sm">12 watt</Button>
    <Button class="text-xs" variant="secondary" size="sm">16 watt</Button>
  </div>

  <div class="flex-1 flex items-center justify-center px-4">
    <div class="flex items-center gap-2 w-full justify-center">
      <div class="flex flex-col items-center gap-1">
        <span class="text-xs text-muted-foreground">Min</span>
        <Button
          size="icon-sm"
          variant="secondary"
          class="rounded-full"
          onclick={() => (brightness = Math.max(0, brightness - 0.05))}
        >
          <Plus size={14} />
        </Button>
      </div>

      <CirclarSlider
        bind:progress={brightness}
        draggable
        size={150}
        strokeWidth={8}
        full
      >
        <div class="flex flex-col items-center">
          <span class="text-2xl font-bold">{Math.round(brightness * 100)}%</span
          >
          <span class="text-xs text-muted-foreground">Intensity</span>
        </div>
      </CirclarSlider>
      <div class="flex flex-col items-center gap-1">
        <span class="text-xs text-muted-foreground">Max</span>
        <Button
          size="icon-sm"
          variant="secondary"
          class="rounded-full"
          onclick={() => (brightness = Math.min(1, brightness + 0.05))}
        >
          <Minus size={14} />
        </Button>
      </div>
    </div>
  </div>

  <div class="flex gap-3 justify-center pb-4 px-4">
    <Button size="icon" variant="secondary" class="rounded-full">
      <Type size={16} />
    </Button>
    <Button size="icon" variant="secondary" class="rounded-full">
      <Sparkles size={16} />
    </Button>
    <Button size="icon" variant="secondary" class="rounded-full">
      <CloudSun size={16} />
    </Button>
  </div>
</Card>

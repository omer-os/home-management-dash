<script lang="ts">
  import type { Snippet } from "svelte";

  const {
    overview,
    controls,
  }: {
    overview: Snippet;
    controls: Snippet;
  } = $props();
</script>

<div class="flex flex-col h-full w-full gap-4">
  <section class="grid gap-4 flex-2/3 grid-cols-4 grid-rows-2 w-full">
    {@render overview()}
  </section>

  <section class="flex flex-1/3 gap-4 w-full">
    {@render controls()}
  </section>
</div>

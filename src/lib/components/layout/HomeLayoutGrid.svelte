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

<div class="flex flex-col flex-1 w-full gap-4">
  <section
    class="grid overflow-hidden gap-4 flex-3/5 grid-cols-4 grid-rows-2 w-full"
  >
    {@render overview()}
  </section>

  <section class="flex flex-2/5 gap-4 w-full">
    {@render controls()}
  </section>
</div>

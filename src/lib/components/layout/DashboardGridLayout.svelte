<script lang="ts">
  import DashLeftPanel from "./DashLeftPanel.svelte";
  import DashNavbar from "./DashNavbar.svelte";

  const { children } = $props();
</script>

<div
  class="h-dvh w-full overflow-hidden grid grid-cols-[auto_1fr] grid-rows-[auto_1fr]"
>
  <DashNavbar />

  <DashLeftPanel />
  <main class="p-4 ps-0">
    {@render children()}
  </main>
</div>

<script lang="ts">
  import DashLeftPanel from "./DashLeftPanel.svelte";
  import DashNavbar from "./DashNavbar.svelte";

  const { children } = $props();
</script>

<div
  class="h-dvh w-full overflow-hidden grid md:grid-cols-[auto_1fr] grid-cols-1 grid-rows-[auto_1fr]"
>
  <DashNavbar />

  <DashLeftPanel />
  <main class="p-4 flex overflow-hidden">
    <main class="flex flex-1 overflow-scroll rounded-4xl">
      {@render children()}
      <div
        class="absolute bg-linear-0 from-background via-background to-transparent z-10 bottom-0 right-0 left-0 h-14"
      ></div>
    </main>
  </main>
</div>

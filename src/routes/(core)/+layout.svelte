<script lang="ts">
  import DashboardGridLayout from "$lib/components/layout/DashboardGridLayout.svelte";

  const { children } = $props();
</script>

<DashboardGridLayout>
  {@render children()}
</DashboardGridLayout>

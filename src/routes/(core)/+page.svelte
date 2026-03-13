<script>
    import HomeLiveFeedCard from "$lib/components/cards/HomeLiveFeedCard.svelte";
  import HomeLayoutGrid from "$lib/components/layout/HomeLayoutGrid.svelte";
  import Card from "$lib/components/ui/card/card.svelte";
</script>

<HomeLayoutGrid>
  {#snippet overview()}
    <HomeLiveFeedCard />
    <Card></Card>
    <Card></Card>
    <Card class="col-span-2"></Card>
  {/snippet}
  {#snippet controls()}
    <Card class="flex-1 h-full"></Card>
    <Card class="flex-1 h-full"></Card>
    <Card class="flex-1 h-full"></Card>
  {/snippet}
</HomeLayoutGrid>

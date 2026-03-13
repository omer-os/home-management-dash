<script>
  import HomeLiveFeedCard from "$lib/components/cards/HomeLiveFeedCard.svelte";
    import HomeMusicPlayerCard from "$lib/components/cards/HomeMusicPlayerCard.svelte";
  import HomeTempCard from "$lib/components/cards/HomeTempCard.svelte";
  import HomeWifiCard from "$lib/components/cards/HomeWifiCard.svelte";
  import HomeLayoutGrid from "$lib/components/layout/HomeLayoutGrid.svelte";
  import Card from "$lib/components/ui/card/card.svelte";
</script>

<HomeLayoutGrid>
  {#snippet overview()}
    <HomeLiveFeedCard />
    <HomeWifiCard />
    <HomeTempCard />
    <HomeMusicPlayerCard />
  {/snippet}
  {#snippet controls()}
    <Card class="flex-1 h-full"></Card>
    <Card class="flex-1 h-full"></Card>
    <Card class="flex-1 h-full"></Card>
  {/snippet}
</HomeLayoutGrid>

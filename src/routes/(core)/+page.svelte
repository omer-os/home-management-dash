<script>
  import HomeAirContainerCard from "$lib/components/cards/HomeAirContainerCard.svelte";
  import HomeBluetoothSpeakerCard from "$lib/components/cards/HomeBluetoothSpeakerCard.svelte";
  import HomeLightingCard from "$lib/components/cards/HomeLightingCard.svelte";
  import HomeLiveFeedCard from "$lib/components/cards/HomeLiveFeedCard.svelte";
  import HomeMusicPlayerCard from "$lib/components/cards/HomeMusicPlayerCard.svelte";
  import HomeTempCard from "$lib/components/cards/HomeTempCard.svelte";
  import HomeWifiCard from "$lib/components/cards/HomeWifiCard.svelte";
  import HomeLayoutGrid from "$lib/components/layout/HomeLayoutGrid.svelte";
</script>

<HomeLayoutGrid>
  {#snippet overview()}
    <HomeLiveFeedCard />
    <HomeWifiCard />
    <HomeTempCard />
    <HomeMusicPlayerCard />
  {/snippet}
  {#snippet controls()}
    <HomeLightingCard />
    <HomeBluetoothSpeakerCard />
    <HomeAirContainerCard />
  {/snippet}
</HomeLayoutGrid>

<script>
  import { WifiIcon } from "@lucide/svelte";
  import CardContent from "../ui/card/card-content.svelte";
  import CardHeader from "../ui/card/card-header.svelte";
  import Card from "../ui/card/card.svelte";
</script>

<Card class="py-0  gap-0 flex flex-col overflow-hidden relative">
  <div class="h-[5em] flex gap-2 p-4">
    <div
      class="rounded-full flex items-center justify-center h-12 w-12 bg-secondary"
    >
      <WifiIcon />
    </div>

    <div class="flex flex-col">
      <p class="font-bold text-xl">Wifi</p>
      <p class="text-muted-foreground text-sm">Hmome_Pulse 5G</p>
    </div>
  </div>

  <div class="flex gap-2 flex-1 items-end">
    <div class="flex flex-col p-4">
      <div class="text-3xl font-medium">120</div>
      <p class="text-muted-foreground font-light text-lg">Mbps</p>
    </div>

    <div class="h-[7em] absolute bottom-0 -end-4">
      <img
        class="h-full scale-x-[-1] w-full object-contain"
        src="https://i.imgur.com/w3bi63n.png"
        alt=""
      />
    </div>
  </div>
</Card>

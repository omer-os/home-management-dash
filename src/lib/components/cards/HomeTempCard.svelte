<script>
  import { Sun, WifiIcon } from "@lucide/svelte";
  import CardContent from "../ui/card/card-content.svelte";
  import CardHeader from "../ui/card/card-header.svelte";
  import Card from "../ui/card/card.svelte";
</script>

<Card class="py-0 flex flex-col overflow-hidden relative">
  <div class="h-[5em] flex gap-2 p-4">
    <div
      class="rounded-full flex items-center justify-center h-12 w-12 bg-secondary"
    >
      <Sun />
    </div>

    <div class="flex flex-col">
      <p class="font-bold text-xl">Pemperature</p>
      <p class="text-muted-foreground text-sm">Iraq, Kirkuk</p>
    </div>
  </div>

  <div class="flex gap-2 flex-1 items-end">
    <div class="flex flex-col p-4">
      <div class="text-3xl font-medium">21°c</div>
      <p class="text-muted-foreground font-light text-lg">Cloudy night</p>
    </div>
  </div>
</Card>

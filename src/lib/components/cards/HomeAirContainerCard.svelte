<script>
  import {
    AirVent,
    Gauge,
    Settings2,
    Snowflake,
    Sun,
    Timer,
    WifiIcon,
  } from "@lucide/svelte";
  import Card from "../ui/card/card.svelte";
  import Button from "../ui/button/button.svelte";
  import CirclarSlider from "../ui/CirclarSlider.svelte";
  import Switch from "../ui/switch/switch.svelte";
</script>

<Card
  class="py-0 md:min-h-auto min-h-[23em] flex-1 flex flex-col overflow-hidden relative"
>
  <div class="flex gap-2 p-4 pb-2 items-center">
    <div
      class="rounded-full flex items-center justify-center h-12 w-12 bg-secondary"
    >
      <AirVent />
    </div>
    <div class="flex flex-1 flex-col">
      <p class="font-medium text-lg">Air Conditioner</p>
      <p class="text-muted-foreground text-sm">Living Room</p>
    </div>

    <div>
      <Switch checked />
    </div>
  </div>

  <div class="flex-1 flex flex-col">
    <div class="mx-auto">
      <CirclarSlider draggable>
        <div class="flex flex-col">
          <p class="text-muted-foreground">Tempreture</p>
          <div class="flex items-end justify-center gap-1">
            <div class="text-5xl font-bold">21</div>
            <span class="text-3xl text-muted-foreground">°c</span>
          </div>
        </div>
      </CirclarSlider>
    </div>
  </div>

  <div class="flex gap-3 overflow-x-auto pb-4 px-4">
    <Button class="text-xs" variant="secondary" size="sm">
      <Settings2 size={14} /> Mode
    </Button>
    <Button class="text-xs" variant="secondary" size="sm">
      <Timer size={14} /> Timer
    </Button>
    <Button class="text-xs" variant="secondary" size="sm">
      <Gauge size={14} /> Speed
    </Button>
    <Button class="text-xs" variant="secondary" size="sm">
      <Snowflake size={14} /> Cold
    </Button>
  </div>
</Card>

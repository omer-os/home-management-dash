<script>
  import {
    ChevronDown,
    Timer,
    Monitor,
    Mic,
    Move,
    Power,
  } from "@lucide/svelte";
  import Button from "../ui/button/button.svelte";
  import Card from "../ui/card/card.svelte";
</script>

<Card
  class="relative p-3 col-span-2 flex gap-2 items-center justify-between row-span-2 overflow-hidden md:h-auto h-[30em]"
>
  <img
    src="https://i.pinimg.com/1200x/63/1a/ee/631aee73a43d43baebb0775867960b69.jpg"
    class="absolute inset-0 object-cover w-full h-full brightness-70"
    alt="room"
  />
  <div class="flex z-10 relative w-full justify-between">
    <div
      class="items-center px-3 py-2 backdrop-blur-2xl bg-gray-100/10 rounded-full flex gap-2"
    >
      <div class="h-3 w-3 bg-destructive rounded-full"></div>
      <p class="text-foreground text-sm font-medium">Live</p>
    </div>
    <div
      class="items-center px-3 py-2 backdrop-blur-2xl bg-gray-100/10 rounded-full flex gap-2"
    >
      <p class="text-foreground text-sm font-medium">Camera 1</p>
      <div>
        <ChevronDown size={15} />
      </div>
    </div>
  </div>
  <div class="flex gap-2">
    <Button
      size="icon-lg"
      class="relative z-10 rounded-full backdrop-blur-lg bg-gray-100/10"
      variant="ghost"
    >
      <Timer />
    </Button>
    <Button
      size="icon-lg"
      class="relative z-10 rounded-full backdrop-blur-lg bg-gray-100/10"
      variant="ghost"
    >
      <Monitor />
    </Button>
    <Button
      size="icon-lg"
      class="relative z-10 rounded-full backdrop-blur-lg bg-gray-100/10"
      variant="ghost"
    >
      <Mic />
    </Button>
    <Button
      size="icon-lg"
      class="relative z-10 rounded-full backdrop-blur-lg bg-gray-100/10"
      variant="ghost"
    >
      <Move />
    </Button>
    <Button size="icon-lg" class="relative z-10 rounded-full" variant="default">
      <Power />
    </Button>
  </div>
</Card>

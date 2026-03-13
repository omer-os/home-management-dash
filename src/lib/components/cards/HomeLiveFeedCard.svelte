<script>
  import { Play, SquareArrowRightExit } from "@lucide/svelte";
  import Button from "../ui/button/button.svelte";
  import Card from "../ui/card/card.svelte";
</script>

<Card
  class="relative p-3 col-span-2 flex gap-2 items-center justify-end row-span-2 overflow-hidden"
>
  <img
    src="https://i.pinimg.com/1200x/a1/14/43/a11443a9e950c58591f083719fcd12b6.jpg"
    class="absolute inset-0 object-cover w-full h-full brightness-80"
    alt="room"
  />

  <div class="flex gap-2">
    <Button
      size="icon-lg"
      class="relative z-10 rounded-full backdrop-blur-2xl bg-gray-300/20"
      variant="ghost"
    >
      <Play />
    </Button>
    <Button
      size="icon-lg"
      class="relative z-10 rounded-full backdrop-blur-2xl bg-gray-300/20"
      variant="ghost"
    >
      <Play />
    </Button>
    <Button
      size="icon-lg"
      class="relative z-10 rounded-full backdrop-blur-2xl bg-gray-300/20"
      variant="ghost"
    >
      <Play />
    </Button>
    <Button
      size="icon-lg"
      class="relative z-10 rounded-full backdrop-blur-2xl bg-gray-300/20"
      variant="ghost"
    >
      <Play />
    </Button>
    <Button size="icon-lg" class="relative z-10 rounded-full" variant="default">
      <SquareArrowRightExit />
    </Button>
  </div>
</Card>

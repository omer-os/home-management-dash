<script>
  import { Heart, Play, SkipBack, SkipForward, StepBack } from "@lucide/svelte";
  import Button from "../ui/button/button.svelte";
  import Card from "../ui/card/card.svelte";
  import Slider from "../ui/slider/slider.svelte";
</script>

<Card
  class="col-span-2 py-4 gap-3 px-4 md:flex-row flex-col md:h-full overflow-hidden"
>
  <div class="aspect-square rounded-3xl overflow-hidden">
    <img
      src="https://i.imgur.com/TJcm7T0.jpeg"
      alt="neon photoshot"
      class="w-full h-full object-cover"
    />
  </div>

  <div class="flex flex-1 flex-col min-w-0">
    <div class="flex w-full gap-3 flex-1 justify-between items-start">
      <div class="flex flex-col min-w-0 flex-1">
        <p class="font-bold truncate text-xl">I'll Love You No Matter What</p>
        <div class="text-muted-foreground text-ms">Mirana Mc-donald</div>
      </div>
      <div class="shrink-0">
        <Button size="icon" variant="secondary">
          <Heart fill="var(--destructive)" color="var(--destructive)" />
        </Button>
      </div>
    </div>
    <div class="flex items-center flex-col">
      <div class="flex w-full gap-3 mt-auto">
        <span class="text-xs text-muted-foreground">00:10</span>
        <Slider type="single" value={5} max={100} step={1} class="flex-1" />
        <span class="text-xs text-muted-foreground">-03:40</span>
      </div>

      <div class="flex gap-2">
        <Button variant="ghost" size="icon" class="">
          <SkipBack class="fill-foreground" />
        </Button>
        <Button variant="default" size="icon" class="">
          <Play class="fill-foreground stroke-0" />
        </Button>
        <Button variant="ghost" size="icon" class="">
          <SkipForward class="fill-foreground" />
        </Button>
      </div>
    </div>
  </div>
</Card>

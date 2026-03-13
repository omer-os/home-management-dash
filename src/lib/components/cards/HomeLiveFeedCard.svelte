<script lang="ts">
  import {
    ChevronDown,
    Timer,
    Monitor,
    Mic,
    Move,
    Power,
    MicOff,
  } from "@lucide/svelte";
  import { Button } from "$lib/components/ui/button/index.js";
  import { Card } from "$lib/components/ui/card/index.js";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";

  type CamType = "cam1" | "cam2" | "cam3" | "cam4";

  const camLabels: Record<CamType, string> = {
    cam1: "Camera 1",
    cam2: "Camera 2",
    cam3: "Camera 3",
    cam4: "Camera 4",
  };

  const camImages: Record<CamType, string> = {
    cam1: "https://i.pinimg.com/1200x/63/1a/ee/631aee73a43d43baebb0775867960b69.jpg",
    cam2: "https://i.pinimg.com/736x/d3/3d/bf/d33dbf6e45628d6dcbb90a1355cc5fca.jpg",
    cam3: "https://i.pinimg.com/736x/dd/04/9a/dd049aa390d5e589d920090ff0682b08.jpg",
    cam4: "https://i.pinimg.com/1200x/39/30/22/39302248a22e2d990df95534af99dff7.jpg",
  };

  let showCamera: CamType = $state("cam1");
  let mic: boolean = $state(true);
</script>

<Card
  class="relative p-3 col-span-2 flex gap-2 items-center justify-between row-span-2 overflow-hidden md:h-auto h-[30em]"
>
  <img
    src={camImages[showCamera]}
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

    <DropdownMenu.Root>
      <DropdownMenu.Trigger
        class="items-center px-3 py-2 backdrop-blur-2xl bg-gray-100/10 rounded-full flex gap-2 cursor-pointer"
      >
        <p class="text-foreground text-sm font-medium">
          {camLabels[showCamera]}
        </p>
        <ChevronDown size={15} />
      </DropdownMenu.Trigger>
      <DropdownMenu.Content>
        {#each Object.entries(camLabels) as [id, label]}
          <DropdownMenu.Item onclick={() => (showCamera = id as CamType)}>
            {label}
          </DropdownMenu.Item>
        {/each}
      </DropdownMenu.Content>
    </DropdownMenu.Root>
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
      variant={"ghost"}
      onclick={() => (mic = !mic)}
    >
      {#if mic}
        <Mic />
      {:else}
        <MicOff />
      {/if}
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

<script>
  import { Sun, WifiIcon } from "@lucide/svelte";
  import Card from "../ui/card/card.svelte";
  import Button from "../ui/button/button.svelte";
  import Switch from "../ui/switch/switch.svelte";
</script>

<Card class="py-0 flex-1 flex flex-col overflow-hidden relative">
  <div class="flex flex-col gap-2">
    <div class="flex gap-2 p-4 pb-2 items-center">
      <div
        class="rounded-full flex items-center justify-center h-12 w-12 bg-secondary"
      >
        <Sun class="fill-foreground" />
      </div>

      <div class="flex flex-1 flex-col">
        <p class="font-medium text-lg">Bluetooth Speaker</p>
        <p class="text-sm text-muted-foreground">Lumo Bean</p>
      </div>

      <div>
        <Switch />
      </div>
    </div>
  </div>

  <div class="flex gap-2 flex-1 p-4 items-end">
    <div class="flex flex-col">
      <p class="text-3xl font-bold">72%</p>
      <p class="text-muted-foreground text-lg">Battery</p>
    </div>

    <div class="absolute h-[13em] w-[13em] -end-6 bottom-0">
      <img src="https://i.imgur.com/9gJddh9.png" alt="speaker" />
    </div>
  </div>
</Card>

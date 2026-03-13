<script>
  import Button from "../ui/button/button.svelte";
  import {
    Home,
    Video,
    CalendarDays,
    Lock,
    Bluetooth,
    Settings,
  } from "@lucide/svelte";
</script>

<div
  class="m-4 p-1 bg-secondary my-auto flex flex-col gap-1 rounded-full w-max h-max"
>
  <Button class="rounded-full h-12 w-12" variant="default" size="icon-lg">
    <Home />
  </Button>
  <Button class="rounded-full h-12 w-12" variant="secondary" size="icon-lg">
    <Video />
  </Button>
  <Button class="rounded-full h-12 w-12" variant="secondary" size="icon-lg">
    <CalendarDays />
  </Button>
  <Button class="rounded-full h-12 w-12" variant="secondary" size="icon-lg">
    <Lock />
  </Button>
  <Button class="rounded-full h-12 w-12" variant="secondary" size="icon-lg">
    <Bluetooth />
  </Button>
  <Button class="rounded-full h-12 w-12" variant="secondary" size="icon-lg">
    <Settings />
  </Button>
</div>

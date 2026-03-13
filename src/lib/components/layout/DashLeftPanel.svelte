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
  class="m-4 md:me-0 md:shadow-none shadow-xl md:static fixed bottom-0 left-1/2 p-1 bg-secondary md:translate-x-0 -translate-x-1/2 md:my-auto flex md:flex-col gap-1 rounded-full w-max h-max z-50"
>
  <Button
    class="rounded-full shadow-none h-12 w-12"
    variant="default"
    size="icon-lg"
  >
    <Home />
  </Button>
  <Button
    class="rounded-full shadow-none h-12 w-12"
    variant="secondary"
    size="icon-lg"
  >
    <Video />
  </Button>
  <Button
    class="rounded-full shadow-none h-12 w-12"
    variant="secondary"
    size="icon-lg"
  >
    <CalendarDays />
  </Button>
  <Button
    class="rounded-full shadow-none h-12 w-12"
    variant="secondary"
    size="icon-lg"
  >
    <Lock />
  </Button>
  <Button
    class="rounded-full shadow-none h-12 w-12"
    variant="secondary"
    size="icon-lg"
  >
    <Bluetooth />
  </Button>
  <Button
    class="rounded-full shadow-none h-12 w-12"
    variant="secondary"
    size="icon-lg"
  >
    <Settings />
  </Button>
</div>

<script>
  import { page } from "$app/state";
  import Button from "../ui/button/button.svelte";
  import {
    Home,
    Video,
    CalendarDays,
    Lock,
    Bluetooth,
    Settings,
  } from "@lucide/svelte";

  const links = [
    { href: "/", icon: Home, route: "/(core)" },
    { href: "/camera", icon: Video, route: "/(core)/camera" },
    { href: "/calendar", icon: CalendarDays, route: "/(core)/calendar" },
    { href: "/access", icon: Lock, route: "/(core)/access" },
    { href: "/bluetooth", icon: Bluetooth, route: "/(core)/bluetooth" },
    { href: "/settings", icon: Settings, route: "/(core)/settings" },
  ];
</script>

<div
  class="md:m-4 mb-4 md:me-0 md:shadow-none shadow-xl md:static fixed bottom-0 left-1/2 p-1 bg-secondary md:translate-x-0 -translate-x-1/2 md:my-auto flex md:flex-col gap-1 rounded-full w-max h-max z-50"
>
  {#each links as { href, icon: Icon, route }}
    <a {href}>
      <Button
        class="rounded-full shadow-none h-12 w-12"
        variant={page.route.id === route ? "default" : "ghost"}
        size="icon-lg"
      >
        <Icon />
      </Button>
    </a>
  {/each}
</div>

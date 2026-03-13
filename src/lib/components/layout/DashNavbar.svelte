<script>
  import {
    Search,
    Moon,
    Sun,
    Bell,
    ChevronDown,
    Sparkles,
  } from "@lucide/svelte";
  import Button from "$lib/components/ui/button/button.svelte";
  import Input from "$lib/components/ui/input/input.svelte";

  let dark = $state(true);

  function toggleTheme() {
    dark = !dark;
    document.documentElement.classList.toggle("dark", dark);
  }
</script>

<nav class="flex w-full col-span-2 items-center justify-between px-6 py-4">
  <div class="flex items-center gap-2">
    <Sparkles size={20} class="text-orange-500 fill-orange-500" />
    <span class="text-lg font-semibold">Smart Home</span>
  </div>

  <div class="relative w-full max-w-md mx-8">
    <Search
      size={16}
      class="absolute left-3 top-1/2 -translate-y-1/2 text-muted-foreground"
    />
    <Input
      placeholder="Search"
      class="pl-9 rounded-full bg-transparent border-border"
    />
  </div>

  <div class="flex items-center gap-3">
    <div class="flex items-center bg-secondary rounded-full p-1">
      <button
        class="rounded-full p-2 transition-colors {dark
          ? 'bg-foreground text-background'
          : ''}"
        onclick={toggleTheme}
      >
        <Moon size={16} />
      </button>
      <button
        class="rounded-full p-2 transition-colors {!dark
          ? 'bg-foreground text-background'
          : ''}"
        onclick={toggleTheme}
      >
        <Sun size={16} />
      </button>
    </div>

    <Button size="icon" variant="ghost" class="rounded-full">
      <Bell size={18} />
    </Button>

    <button
      class="flex items-center gap-2 pl-1 pr-2 py-1 rounded-full hover:bg-secondary transition-colors"
    >
      <img
        src="https://i.pravatar.cc/32?img=12"
        alt="avatar"
        class="h-8 w-8 rounded-full object-cover"
      />
      <div class="flex flex-col text-left">
        <span class="text-sm font-medium leading-tight">Ethan Maxwell</span>
        <span class="text-xs text-muted-foreground leading-tight">Admin</span>
      </div>
      <ChevronDown size={14} class="text-muted-foreground" />
    </button>
  </div>
</nav>

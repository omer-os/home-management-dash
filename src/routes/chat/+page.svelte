<script lang="ts">
  import Button from "$lib/components/ui/button/button.svelte";
  import DropdownMenuTrigger from "$lib/components/ui/dropdown-menu/dropdown-menu-trigger.svelte";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index";
  import * as InputGroup from "$lib/components/ui/input-group/index.js";
  import {
    ArrowUpIcon,
    AudioLines,
    ChevronDown,
    Code,
    CoffeeIcon,
    GraduationCapIcon,
    InfoIcon,
    Lightbulb,
    Pen,
    Plus,
    Sidebar,
    Voicemail,
  } from "@lucide/svelte";

  let chatSuggestions = [
    {
      icon: Pen,
      label: "Write",
    },
    {
      icon: GraduationCapIcon,
      label: "learn",
    },
    {
      icon: Code,
      label: "Code",
    },
    {
      icon: CoffeeIcon,
      label: "Coffe",
    },
    {
      icon: Lightbulb,
      label: "Claude's choice",
    },
  ];
</script>

<div
  class="h-dvh flex flex-col relative bottom-[3.19em] w-full overflow-hidden"
>
  <!-- top bar -->
  <div class="flex justify-between p-2 items-center">
    <Button size="icon" variant="ghost">
      <Sidebar />
    </Button>

    <Button size="icon" variant="ghost">
      <InfoIcon />
    </Button>
  </div>

  <!-- content area -->
  <div class="flex flex-col items-center justify-center flex-1">
    <h1 class="text-3xl text-center">Sunday session, omar?</h1>

    <!-- chat ui area -->

    <div class="mt-[2.2em]">
      <InputGroup.Root class="w-[42.1em] p-[0.54rem] pb-1">
        <InputGroup.Textarea
          class="placeholder:text-[1.12em]"
          placeholder="How can i help you today?"
        />
        <InputGroup.Addon
          class="justify-between items-center"
          align="block-end"
        >
          <InputGroup.Button variant="ghost" size="icon-sm">
            <Plus />
          </InputGroup.Button>

          <div class="flex gap-2">
            <DropdownMenu.Root>
              <DropdownMenu.Trigger class="flex gap-1 items-center"
                >Opus 4.6 Extended <ChevronDown
                  size={15}
                /></DropdownMenu.Trigger
              >
              <DropdownMenu.Content
                side="top"
                align="start"
                class="[--radius:0.95rem]"
              >
                <DropdownMenu.Item>Auto</DropdownMenu.Item>
                <DropdownMenu.Item>Agent</DropdownMenu.Item>
                <DropdownMenu.Item>Manual</DropdownMenu.Item>
              </DropdownMenu.Content>
            </DropdownMenu.Root>
            <InputGroup.Button variant="ghost" size="icon-sm">
              <AudioLines />
            </InputGroup.Button>
          </div>
        </InputGroup.Addon>
      </InputGroup.Root>
    </div>

    <div class="flex gap-2 mt-4">
      {#each chatSuggestions as suggestion}
        <Button variant="outline" class="flex items-center gap-2">
          <suggestion.icon size={16} />
          {suggestion.label}
        </Button>
      {/each}
    </div>
  </div>
</div>

<script>
  import Button from "../ui/button/button.svelte";
  import { Home, RedoIcon } from "@lucide/svelte";
</script>

<div class="m-4 flex flex-col gap-1 bg-secondary rounded-full w-max h-max">
  <Button class="rounded-full" variant="default" size="icon-lg">
    <Home />
  </Button>
  <Button class="rounded-full" variant="secondary" size="icon-lg">
    <RedoIcon />
  </Button>
</div>

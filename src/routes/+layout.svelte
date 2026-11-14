<script lang="ts">
  import "./layout.css";
  import favicon from "#lib/assets/favicon.svg";
  import { ModeWatcher } from "mode-watcher";
  import { Toaster } from "#lib/components/ui/sonner/index.js";
  import { TooltipProvider } from "#lib/components/ui/tooltip/index.js";
  import type { LayoutProps } from "./$types";

  let { children }: LayoutProps = $props();
</script>

<svelte:head>
  <link rel="icon" href={favicon} />
  <title>miaulabs :: home</title>
</svelte:head>

<ModeWatcher />
<Toaster position="top-right" />
<TooltipProvider>
  <div class="flex min-h-dvh flex-col items-center justify-center">
    {@render children()}
  </div>
</TooltipProvider>

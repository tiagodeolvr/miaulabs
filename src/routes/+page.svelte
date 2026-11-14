<script>
  import { ModeToggle } from "#lib/components/ui/mode-toggle/index.js";
  import { toast } from "svelte-sonner";
  import { resolve } from "$app/paths";
  import * as Tooltip from "#lib/components/ui/tooltip/index.js";
  import { toggleMode } from "mode-watcher";
  import { Button } from "#lib/components/ui/button/index.js";
  import UserIcon from "phosphor-svelte/lib/UserIcon";
</script>

<header
  class="sticky top-0 z-10 flex min-w-dvw flex-col items-center justify-center border bg-sidebar shadow"
>
  <nav class="container flex h-14 items-center justify-between gap-4 px-4">
    <a
      href={resolve("/")}
      onclick={() => toast("Welcome!")}
      class="font-heading text-xl font-semibold text-foreground/90 hover:text-accent-foreground"
    >
      miaulabs
    </a>
    <ul class="flex items-center justify-center gap-2">
      <li>
        <Tooltip.Root>
          <Tooltip.Trigger>
            <ModeToggle />
          </Tooltip.Trigger>
          <Tooltip.Content>
            <p>melhor fechar os olhos!</p>
          </Tooltip.Content>
        </Tooltip.Root>
      </li>

      <li>
        <Button variant="ghost" type="button" href={resolve("/")}>Cadastrar</Button>
      </li>
      <li>
        <Button variant="outline" type="button" href={resolve("/dashboard")}>
          <UserIcon />
          Entrar
        </Button>
      </li>
    </ul>
  </nav>
</header>
<main class="mx-auto flex-1 leading-loose"></main>
<footer class="sticky bottom-0 z-10 container mx-auto flex items-center justify-center gap-1">
  <button type="button" aria-label="toggle dark mode" tabindex={-1} onclick={toggleMode}>
    <span class="text-md inline-flex align-text-top font-mono text-muted-foreground"> &copy; </span>
    <p class="inline-flex font-mono text-xs text-muted-foreground">
      2025 miaulabs. Todos os direitos reservados.
    </p>
  </button>
</footer>

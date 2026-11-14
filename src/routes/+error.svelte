<script lang="ts">
  import { resolve } from "$app/paths";
  import { Button } from "#lib/components/ui/button/index.js";
</script>

<div class="flex min-h-dvh min-w-dvw flex-col items-center justify-center scroll-smooth">
  <h1 class="font-mono text-3xl font-bold">404</h1>
  <div class="flex flex-col items-center p-2">
    <p class="text-center text-sm text-muted-foreground">Ooops!<br />Página não encontrada</p>
  </div>
  <Button variant="outline" href={resolve("/")} class="m-2">Voltar</Button>
</div>

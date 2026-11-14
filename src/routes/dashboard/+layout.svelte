<script lang="ts">
  import * as Sidebar from "#lib/components/ui/sidebar/index.js";
  import SignOutIcon from "phosphor-svelte/lib/SignOutIcon";
  import IntersectIcon from "phosphor-svelte/lib/IntersectIcon";
  import { resolve } from "$app/paths";

  let { children } = $props();
</script>

<Sidebar.Provider>
  <Sidebar.Root>
    <Sidebar.Header>
      <Sidebar.Menu>
        <Sidebar.MenuItem>
          <Sidebar.MenuButton size="lg" class="border">
            <div class="aspect-square size-10">
              <IntersectIcon
                weight="duotone"
                class="aspect-square min-h-full min-w-full p-1 text-primary"
              >
                <animate attributeName="opacity" values="0;1;0" dur="4s" repeatCount="indefinite">
                </animate>
                <animateTransform
                  attributeName="transform"
                  attributeType="XML"
                  type="rotate"
                  dur="5s"
                  from="0 0 0"
                  to="360 0 0"
                  repeatCount="indefinite"
                ></animateTransform>
              </IntersectIcon>
            </div>
            <div class="flex items-center gap-2 px-2">
              <span class="truncate font-mono font-medium">Miau Labs</span>
            </div>
          </Sidebar.MenuButton>
        </Sidebar.MenuItem>
      </Sidebar.Menu>
    </Sidebar.Header>

    <Sidebar.Content />

    <Sidebar.Footer>
      <Sidebar.Menu>
        <Sidebar.MenuItem>
          <Sidebar.MenuButton>
            <a href={resolve("/")} class="min-h-full min-w-full">
              <SignOutIcon class="mr-2 inline-block" />
              Sair
            </a>
          </Sidebar.MenuButton>
        </Sidebar.MenuItem>
      </Sidebar.Menu>
    </Sidebar.Footer>
  </Sidebar.Root>

  <main class="p-4 leading-loose">
    <Sidebar.Trigger />

    {@render children?.()}
  </main>
</Sidebar.Provider>

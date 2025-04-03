<script lang="ts">
  import Icon from "@iconify/svelte";
  import ThemeToggle from "./ThemeToggle.svelte";

  const links = [
    { name: "About", href: "#about" },
    { name: "Projects", href: "#projects" },
    { name: "Work Experience", href: "#work-experience" },
    { name: "Connect", href: "#connect" }
  ];

  // Function to close the drawer
  function closeDrawer() {
    const drawerCheckbox = document.getElementById(
      "my-drawer-3"
    ) as HTMLInputElement;
    if (drawerCheckbox) {
      drawerCheckbox.checked = false;
    }
  }
</script>

<div class="drawer">
  <input id="my-drawer-3" type="checkbox" class="drawer-toggle" />
  <div class="drawer-content flex flex-col">
    <!-- Navbar -->
    <div class="navbar w-full bg-base-300 dark:bg-base-100 shadow-md">
      <div class="flex-none md:hidden">
        <label
          for="my-drawer-3"
          aria-label="open sidebar"
          class="btn btn-square btn-ghost"
        >
          <Icon icon="mdi:menu" width="24" />
        </label>
      </div>
      <div class="mx-2 flex-1 px-2 md:flex-none">
        <span class="text-xl font-bold">aribfarooqui.dev</span>
      </div>
      <div class="hidden flex-1 justify-center md:flex">
        <ul class="menu menu-horizontal rounded-box gap-1">
          {#each links as link}
            <li>
              <a
                href={link.href}
                class="rounded-lg px-4 py-2 font-medium transition-all hover:bg-primary/25"
              >
                {link.name}
              </a>
            </li>
          {/each}
        </ul>
      </div>
      <div class="flex-none">
        <ThemeToggle />
      </div>
    </div>
  </div>
  <div class="drawer-side z-[60]">
    <label for="my-drawer-3" aria-label="close sidebar" class="drawer-overlay"
    ></label>
    <ul
      class="menu bg-base-300 dark:bg-base-100 min-h-full w-80 p-6 pt-8 text-base-content"
    >
      <li>
        <a
          href="/"
          class="text-xl font-bold hover:text-primary"
          on:click={closeDrawer}
        >
          aribfarooqui.dev
        </a>
      </li>
      <div class="divider"></div>
      {#each links as link}
        <li class="my-1">
          <a
            href={link.href}
            class="rounded-lg py-3 font-medium active:bg-primary/20 active:text-primary"
            on:click={closeDrawer}
          >
            {link.name}
          </a>
        </li>
      {/each}
    </ul>
  </div>
</div>

<script lang="ts">
  import { onMount } from "svelte";
  let toggled = false;

  // Load theme preference from localStorage on component mount
  onMount(() => {
    const savedTheme = localStorage.getItem("theme");

    // Check if there's a saved preference
    if (savedTheme) {
      toggled = savedTheme === "dark";
    } else {
      // If no saved preference, check user's system preference
      toggled = window.matchMedia("(prefers-color-scheme: dark)").matches;
    }

    // Apply the theme on initial load
    applyTheme(toggled);
  });

  function toggleTheme() {
    toggled = !toggled;
    applyTheme(toggled);
  }

  function applyTheme(isDark: boolean) {
    // Save preference to localStorage
    localStorage.setItem("theme", isDark ? "dark" : "light");

    // Apply theme to document
    document.documentElement.classList.toggle("dark", isDark);
    document.documentElement.classList.toggle("light", !isDark);
    document.documentElement.setAttribute(
      "data-theme",
      isDark ? "dark" : "light"
    );
  }
</script>

<button
  class="theme-toggle {toggled ? 'theme-toggle--toggled' : ''}"
  type="button"
  title="Toggle theme"
  aria-label="Toggle theme"
  on:click={toggleTheme}
>
  <svg
    xmlns="http://www.w3.org/2000/svg"
    aria-hidden="true"
    width="2em"
    height="2em"
    fill="currentColor"
    stroke-linecap="round"
    class="theme-toggle__classic"
    viewBox="0 0 32 32"
  >
    <clipPath id="theme-toggle__classic__cutout">
      <path d="M0-5h30a1 1 0 0 0 9 13v24H0Z" />
    </clipPath>
    <g clip-path="url(#theme-toggle__classic__cutout)">
      <circle cx="16" cy="16" r="9.34" />
      <g stroke="currentColor" stroke-width="1.5">
        <path d="M16 5.5v-4" />
        <path d="M16 30.5v-4" />
        <path d="M1.5 16h4" />
        <path d="M26.5 16h4" />
        <path d="m23.4 8.6 2.8-2.8" />
        <path d="m5.7 26.3 2.9-2.9" />
        <path d="m5.8 5.8 2.8 2.8" />
        <path d="m23.4 23.4 2.9 2.9" />
      </g>
    </g>
  </svg>
</button>

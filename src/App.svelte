<script lang="ts">
  import Icon from "@iconify/svelte";
  import About from "./components/About.svelte";
  import Connect from "./components/Connect.svelte";
  import Hero from "./components/Hero.svelte";
  import Navbar from "./components/Navbar.svelte";
  import Projects from "./components/Projects.svelte";
  import WorkExperience from "./components/WorkExperience.svelte";

  const year = new Date().getFullYear();
</script>

<Navbar />

<main>
  <Hero />
  <About />
  <Projects />
  <WorkExperience />
  <Connect />
</main>

<footer class="bg-base-300 py-8 text-center">
  <div class="container mx-auto px-4">
    <p class="text-base-content text-opacity-80">
      &copy; {new Date().getFullYear()} All Rights Reserved | Created by Arib Farooqui
    </p>
    <p class="mt-2 text-sm text-base-content text-opacity-60">
      Built with Svelte and DaisyUI
    </p>
    <div class="flex justify-center mt-0.5">
      <button
        class="btn btn-ghost btn-circle hover:btn-primary"
        on:click={() => window.scrollTo(0, 0)}
      >
        <Icon icon="mdi:arrow-up-bold-circle" width="24" />
      </button>
    </div>
  </div>
</footer>

<style>
</style>

<script>
  import Icon from "@iconify/svelte";

  const links = [
    {
      label: "LinkedIn",
      url: "https://www.linkedin.com/in/aribfarooqui/",
      icon: "linkedin"
    },
    {
      label: "Resume",
      url: "/resume.pdf", // Ensure this file is in the static/public folder
      icon: "file-text"
    },
    {
      label: "GitHub",
      url: "https://github.com/aribbabar",
      icon: "github"
    }
  ];
</script>

<section id="connect" class="py-16 md:py-20 bg-base-100">
  <div class="max-w-2xl mx-auto px-4 text-center">
    <h2 class="text-3xl font-bold mb-6 md:mb-8">Connect</h2>
    <div class="flex flex-wrap justify-center gap-4 md:gap-6">
      {#each links as link}
        <a
          href={link.url}
          target="_blank"
          rel="noopener noreferrer"
          class="btn btn-outline gap-2 min-w-[120px] text-sm md:text-base"
        >
          <Icon
            icon="mdi:{link.icon}"
            width="20"
            height="20"
            class="md:w-6 md:h-6"
          />
          {link.label}
        </a>
      {/each}
    </div>
  </div>
</section>

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

<section id="connect" class="py-20 bg-base-100">
  <div class="max-w-2xl mx-auto px-4 text-center">
    <h2 class="text-3xl font-bold mb-8">Connect</h2>
    <div class="flex justify-center gap-6">
      {#each links as link}
        <a href={link.url} target="_blank" class="btn btn-outline gap-2">
          <Icon icon="mdi:{link.icon}" width="24" />
          {link.label}
        </a>
      {/each}
    </div>
  </div>
</section>

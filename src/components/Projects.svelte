<script>
  // You can later replace this with a dynamic array or fetch
  const projects = [
    {
      title: "Vector Cash",
      description:
        "VectorCash is a personal finance tracker that allows users to log, visualize, and manage their financial accounts. With an intuitive interface and real-time charting, users can monitor their assets, liabilities, and net worth effortlessly.",
      link: "https://github.com/aribbabar/vector-cash",
      image: "/vector_cash.svg",
    },
    {
      title: "DBZ: The Card Game",
      description:
        "DBZ: The Card Game is a web-based card game inspired by the Dragon Ball Z universe.",
      link: "https://aribbabar.github.io/dbzcardgame/",
      image: "/dbz.jpg",
    },
  ];
</script>

<section id="projects" class="py-20 bg-base-100">
  <div class="max-w-6xl mx-auto px-4">
    <h2 class="text-3xl font-bold text-center mb-12">Projects</h2>

    <div class="grid gap-10 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
      {#each projects as project}
        <div
          class="card bg-base-200 shadow-xl hover:shadow-2xl transition-shadow"
        >
          <figure class="h-48 overflow-hidden">
            <img
              src={project.image}
              alt={project.title}
              class="object-cover w-full h-full"
            />
          </figure>
          <div class="card-body">
            <h3 class="card-title">{project.title}</h3>
            <p>{project.description}</p>
            <div class="card-actions justify-end">
              <a
                href={project.link}
                target="_blank"
                class="btn btn-sm btn-primary">View Project</a
              >
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

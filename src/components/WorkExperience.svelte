<script lang="ts">
  // Define the interface for experience objects
  interface Experience {
    role: string;
    company: string;
    startDate: string;
    endDate: string;
    period: string;
    description: string;
    duration?: string;
  }

  // Helper function to calculate the time duration between dates
  function calculateDuration(startDate: string, endDate: string) {
    const start = new Date(startDate);
    const end = endDate === "Present" ? new Date() : new Date(endDate);

    const years = end.getFullYear() - start.getFullYear();
    const months = end.getMonth() - start.getMonth();

    let totalMonths = years * 12 + months;
    if (end.getDate() < start.getDate()) {
      totalMonths--;
    }

    const calculatedYears = Math.floor(totalMonths / 12);
    const calculatedMonths = totalMonths % 12;

    let result = "";
    if (calculatedYears > 0) {
      result += `${calculatedYears} ${calculatedYears === 1 ? "year" : "years"}`;
    }
    if (calculatedMonths > 0) {
      if (result) result += " ";
      result += `${calculatedMonths} ${calculatedMonths === 1 ? "month" : "months"}`;
    }
    if (!result) result = "Less than a month";

    return result;
  }

  // Parse date format from "MMM YYYY" to a Date object
  function parseDate(dateStr: string) {
    if (dateStr === "Present") return "Present";
    const [month, year] = dateStr.split(" ");
    const monthIndex = [
      "Jan",
      "Feb",
      "Mar",
      "Apr",
      "May",
      "Jul",
      "Aug",
      "Sep",
      "Oct",
      "Nov",
      "Dec"
    ].indexOf(month);
    return new Date(parseInt(year), monthIndex, 1).toISOString();
  }

  const experiences: Experience[] = [
    {
      role: "Jr. Software Developer",
      company: "Impresst Business Services",
      startDate: "Apr 2025",
      endDate: "Present",
      period: "Apr 2025 – Present",
      description:
        "Contributed to the development of a web-based ERP system using ASP.NET. Collaborated with cross-functional teams to enhance user experience and optimize performance."
    },
    {
      role: "Associate",
      company: "JCPenney",
      startDate: "Aug 2022",
      endDate: "Present",
      period: "Aug 2022 - Present",
      description:
        "Provided exceptional customer service and support in a fast-paced retail environment. Assisted in inventory management and merchandising efforts."
    },
    {
      role: "IT Specialist",
      company: "Q Computers",
      startDate: "Jun 2024",
      endDate: "Jan 2025",
      period: "Jun 2024 – Jan 2025",
      description:
        "Provided technical support and troubleshooting for hardware and software issues. Assisted in the setup and maintenance of computer systems and networks."
    }
  ];

  // Calculate duration for each experience
  experiences.forEach((exp) => {
    exp.duration = calculateDuration(
      parseDate(exp.startDate),
      parseDate(exp.endDate)
    );
  });
</script>

<section id="work-experience" class="py-20 bg-base-200">
  <div class="max-w-4xl mx-auto px-4">
    <h2 class="text-3xl font-bold text-center mb-12">Work Experience</h2>

    <div class="space-y-8">
      {#each experiences as exp}
        <div
          class="bg-base-100 p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow"
        >
          <div
            class="flex flex-col md:flex-row md:justify-between md:items-start gap-1 mb-3"
          >
            <div>
              <h3 class="text-xl font-semibold">{exp.role} @ {exp.company}</h3>
              <div class="flex flex-wrap items-center gap-x-2 mt-1">
                <span class="text-sm text-opacity-90">{exp.period}</span>
              </div>
            </div>
            <div class="order-first md:order-last">
              <span
                class="inline-block bg-primary text-white text-xs font-medium px-2.5 py-1 rounded"
              >
                {exp.duration}
              </span>
            </div>
          </div>
          <p class="text-base-content text-opacity-80">{exp.description}</p>
        </div>
      {/each}
    </div>
  </div>
</section>

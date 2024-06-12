<script>
    import Header from './Header.svelte';
    import Contact from './Contact.svelte';
    import Education from './Education.svelte';
    import Experience from './Experience.svelte';
    import Volunteer from './Volunteer.svelte';
    import Skills from './Skills.svelte';
    import Tools from './Tools.svelte';
    import Languages from './Languages.svelte';
    import ThemeToggle from './ThemeToggle.svelte';
    import ContactForm from './ContactForm.svelte';

    const name = "Ibrahim Ouarzane";
    const title = "Financial Analyst";
    const imgSrc = "https://i.ibb.co/5TNW0PH/ibrahim-ouarzane.jpg";

    const email = "Ibrahim@essec.com";
    const phone = "0221654988";
    const degree = "Master in Management";
    const school = "Essec Business School";
    const graduationYear = "2024";
    const experiences = [
        {
            position: "Market Analyst",
            year: "2021",
            company: "Sysnav",
            details: [
                "Developed prototypes for a new solution to address elderly falls and set up the environment for real tests.",
                "Established partnerships with 5 of the biggest EHPADs in France for testing purposes."
            ]
        },
        {
            position: "Project Leader - Process Automation",
            year: "2022",
            company: "Sysnav",
            details: [
                "Successfully led a project to automate multiple processes using PowerBI & Knime."
            ]
        }
    ];
    const volunteerWork = "Helping middle school students from non-favored neighborhoods with their homework and boosting their confidence.";
    const skills = ["Finance", "Transformation", "Project Management", "Digitalization of Processes", "Tough Negotiations"];
    const tools = [
        { name: "Excel", proficiency: "Professional" },
        { name: "Knime", proficiency: "Professional" },
        { name: "PowerBI", proficiency: "Professional" },
        { name: "Python", proficiency: "Intermediate" }
    ];
    const languages = [
        { name: "French", proficiency: "Fluent", level: 4 },
        { name: "Arabic", proficiency: "Fluent", level: 3 },
        { name: "English", proficiency: "Fluent", level: 4 }
    ];

    function handleFormSubmit(event) {
        const { name, email, message } = event.detail;
        alert('Your message has been successfully sent.');
    }
</script>

<main class="max-w-3xl mx-auto p-5 relative text-black dark:text-white">
    <div class="absolute top-0 left-0 w-2 bg-black dark:bg-white h-full"></div>
    <div class="w-full sm:w-11/12 md:w-10/12 lg:w-9/12 xl:w-8/12 mx-auto my-8 px-4 py-2 rounded-lg bg-white dark:bg-gray-900">
        <ThemeToggle />
        <Header {name} {title} {imgSrc} />
        <Contact {email} {phone} />
        <Education {degree} {school} {graduationYear} />
        <Experience {experiences} />
        <Volunteer {volunteerWork} />
        <div class="flex flex-wrap justify-between mb-8">
            <div class="w-full sm:w-1/2 mb-4 pr-4 flex flex-col">
                <Skills {skills} />
            </div>
            <div class="w-full sm:w-1/2 mb-10 sm:self-end flex flex-col">
                <Tools {tools} />
            </div>
        </div>
        <Languages {languages} />
        <ContactForm on:submit={handleFormSubmit} />
    </div>
</main>

<style>
    :global(.dark) {
        --bg-color: #333;
        --text-color: #f3f4f6;
        --border-color: #444;
    }

    :global(body) {
        transition: background-color 0.3s, color 0.3s;
    }

    :global(body.dark) {
        background-color: var(--bg-color);
        color: var(--text-color);
    }

    :global(.dark .bg-white) {
        background-color: var(--bg-color);
    }

    :global(.dark .text-black) {
        color: var(--text-color);
    }

    :global(.dark .border-black) {
        border-color: var(--border-color);
    }
</style>

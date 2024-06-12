<script>
    export let experiences;
</script>

<section class="mb-8">
    <h2 class="text-xl font-bold">Experience</h2>
    <ul class="list-none p-0">
        {#each experiences as experience}
            <li class="mb-4">
                <div class="flex justify-between">
                    <strong>{experience.position}</strong>
                    <span class="italic">{experience.year}</span>
                </div>
                <em class="block">{experience.company}</em>
                {#each experience.details as detail}
                    <p class="mt-1">{detail}</p>
                {/each}
            </li>
        {/each}
    </ul>
</section>

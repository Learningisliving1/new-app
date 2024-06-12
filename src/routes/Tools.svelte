<script>
    export let tools;
</script>

<section>
    <h2 class="text-xl font-bold mb-4">Tools</h2>
    <ul class="list-disc list-inside">
        {#each tools as tool}
            <li>
                <span class="inline-block">{tool.name}</span>
                <span class="italic ml-6">({tool.proficiency})</span>
            </li>
        {/each}
    </ul>
</section>

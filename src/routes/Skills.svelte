<script>
    export let skills;
</script>

<section>
    <h2 class="text-xl font-bold mb-4">Skills</h2>
    <ul class="list-disc list-inside">
        {#each skills as skill}
            <li>{skill}</li>
        {/each}
    </ul>
</section>

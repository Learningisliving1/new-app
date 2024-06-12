<script>
    export let languages;
</script>

<section class="w-full sm:w-1/2 mb-4">
    <h2 class="text-xl font-bold mb-4">Languages</h2>
    <ul class="list-disc list-inside">
        {#each languages as language}
            <li class="mb-2">
                <div class="flex justify-between items-center">
                    <span>{language.name}</span>
                    <span class="italic ml-2">({language.proficiency})</span>
                </div>
                <div class="relative w-full h-4 bg-gray-200 rounded">
                    <div class="absolute top-0 left-0 h-4 bg-green-500 rounded" style="width: {language.level * 25}%"></div>
                </div>
            </li>
        {/each}
    </ul>
</section>

<style>
    .progress-bar {
        height: 100%;
        border-radius: inherit;
    }
</style>

<script>
    export let name;
    export let title;
    export let imgSrc;
</script>

<header class="text-center mb-8">
    <!-- svelte-ignore a11y-img-redundant-alt -->
    <img src={imgSrc} alt="Profile Picture" class="w-24 h-24 mx-auto mb-4 rounded-full border-2 border-black dark:border-white">
    <h1 class="text-3xl font-bold">{name}</h1>
    <p class="text-lg">{title}</p>
</header>

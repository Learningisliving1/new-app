<script>
    let isDarkMode = false;

    if (typeof window !== 'undefined' && typeof localStorage !== 'undefined') {
        if (localStorage.getItem('theme') === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
            isDarkMode = true;
            document.documentElement.classList.add('dark');
        } else {
            document.documentElement.classList.remove('dark');
        }
    }

    function toggleTheme() {
        isDarkMode = !isDarkMode;
        if (typeof window !== 'undefined' && typeof localStorage !== 'undefined') {
            if (isDarkMode) {
                document.documentElement.classList.add('dark');
                localStorage.setItem('theme', 'dark');
            } else {
                document.documentElement.classList.remove('dark');
                localStorage.setItem('theme', 'light');
            }
        }
    }
</script>

<button on:click={toggleTheme} class="p-2 bg-gray-200 dark:bg-gray-800 rounded">
    {#if isDarkMode}
        🌙 Dark Mode
    {:else}
        ☀️ Light Mode
    {/if}
</button>

<style>
    button {
        cursor: pointer;
    }
</style>

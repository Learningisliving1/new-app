<script>
    import { createEventDispatcher } from 'svelte';

    let name = '';
    let email = '';
    let message = '';
    let nameError = '';
    let emailError = '';
    let messageError = '';

    const dispatch = createEventDispatcher();

    function validateName() {
        nameError = name.length >= 3 ? '' : 'Name must be at least 3 characters long.';
    }

    function validateEmail() {
        const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        emailError = emailPattern.test(email) ? '' : 'Invalid email address.';
    }

    function validateMessage() {
        messageError = message.length >= 10 ? '' : 'Message must be at least 10 characters long.';
    }

    function handleSubmit(event) {
        event.preventDefault();
        validateName();
        validateEmail();
        validateMessage();
        if (!nameError && !emailError && !messageError) {
            dispatch('submit', { name, email, message });
        }
    }
</script>

<form on:submit={handleSubmit} class="space-y-4">
    <div>
        <label for="name" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Name</label>
        <input id="name" type="text" bind:value={name} on:input={validateName} class="mt-1 p-2 block w-full border border-gray-300 rounded-md dark:bg-gray-800 dark:text-white" />
        {#if nameError}
            <p class="text-red-600 text-sm">{nameError}</p>
        {/if}
    </div>
    <div>
        <label for="email" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Email</label>
        <input id="email" type="email" bind:value={email} on:input={validateEmail} class="mt-1 p-2 block w-full border border-gray-300 rounded-md dark:bg-gray-800 dark:text-white" />
        {#if emailError}
            <p class="text-red-600 text-sm">{emailError}</p>
        {/if}
    </div>
    <div>
        <label for="message" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Message</label>
        <textarea id="message" bind:value={message} on:input={validateMessage} class="mt-1 p-2 block w-full border border-gray-300 rounded-md dark:bg-gray-800 dark:text-white"></textarea>
        {#if messageError}
            <p class="text-red-600 text-sm">{messageError}</p>
        {/if}
    </div>
    <button type="submit" class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-700">Submit</button>
</form>

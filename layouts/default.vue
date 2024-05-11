<template>
    <div class="container mx-auto max-w-2xl">
        <theHeader />
        <main class="p-2 mt-10">
            <slot/>
        </main>
    </div>
</template>

<script setup>
</script>


<style>
body {
    font-family: "Roboto";
    @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-300
}
</style>

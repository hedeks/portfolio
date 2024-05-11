<template>
    <header class="flex justify-between items-center pt-4 pb-4">
        <div class="flex items-center space-x-12">
            <div>
                <nuxt-link to="/" class="text-xl font-semibold p-2 hover:bg-gray-200">Khitsko Kirill</nuxt-link>
            </div>
            <nav class="font-mono">
                <ul class="flex space-x-4">
                    <li>
                        <nuxt-link to="/" class="link">Main</nuxt-link>
                    </li>
                    <li>
                        <nuxt-link to="/about" class="link">About</nuxt-link>
                    </li>
                    <li>
                        <nuxt-link to="/projects" class="link">Projects</nuxt-link>
                    </li>
                </ul>
            </nav>
        </div>

        <ClientOnly>
            <ColorModeSelector />
        </ClientOnly>
    </header>
</template>

<style scoped>
.link {
    @apply p-1 hover:bg-gray-200;
}
</style>
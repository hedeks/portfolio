<template>
    <div class="flex space-x-2 items-center">
        <div v-if="showNextModeLabel" class="text-gray-500 text-xs">
            Change to {{ nextMode }}
        </div>
        <button @mouseenter="showNextModeLabel = true;" @mouseleave="showNextModeLabel = false;" @click="toggleMode" class="hover:bg-gray-100 dark:hover:bg-gray-600 px-2 py-1 text-gray-500">
            {{ nextModeIcon }}
        </button>
    </div>
</template>

<script setup>
const colorMode = useColorMode();
const showNextModeLabel = ref(false);
const modes = [
    "system",
    "light",
    "dark"
];
const nextModeIcons = {
    system: '🌓',
    light: '🌕',
    dark: '🌑'
}
const nextMode = computed(() => {
    const currentModeIndex = modes.indexOf(colorMode.preference);
    const nextModeIndex = currentModeIndex + 1 > modes.length - 1 ? 0 : currentModeIndex + 1;

    return modes[nextModeIndex]
});

const nextModeIcon = computed(() => nextModeIcons[nextMode.value])
const toggleMode = () => {
    colorMode.preference = nextMode.value;
}

</script>
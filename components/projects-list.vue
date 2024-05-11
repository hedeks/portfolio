<template>
    <p class="mb-10">Take a look at my Github projects!</p>

    <section v-if="pending">
        Loading....
    </section>
    <section v-else-if="error">
        Error.... {{ error }}
    </section>
    <section v-else>
        <ul class="grid grid-cols-1 gap-4">
            <li v-for="item in repos" :key="item.id"
                class="border border-gray-200 rounded-sm p-4 hover:bg-gray-100 font-mono">
                <a :href="item.html_url" target="_blank">
                    <div class="flex items-center justify-between">
                        <div class="font-semibold">
                            {{ item.name }}
                        </div>
                        <div>
                            {{ (new Date(item.created_at)).getFullYear() }}
                        </div>
                    </div>
                    <p class="text-sm">
                        {{ item.description }}
                    </p>
                </a>
            </li>
        </ul>
    </section>
</template>


<script setup>
const { error, pending, data } = await useFetch('https://api.github.com/users/hedeks/repos');

const repos = computed(
    () => data.value.sort((a, b) => Date.parse(b.created_at) - Date.parse(a.created_at)
    )
)
</script>
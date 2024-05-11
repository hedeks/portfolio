<template>
    <div>
        <h1>index</h1>
    </div>
</template>


<script setup>

useSeoMeta({
  title: 'Main Page',
  description: 'This is the main page',
  ogTitle: 'Main Page',
  ogDescription: 'This is the main page',
  ogImage: '/favicon.ico',
  ogUrl: 'localhost)',
  twitterTitle: 'Main Page',
  twitterDescription: 'This is the main page',
  twitterImage: '/favicon.ico',
  twitterCard: 'summary'
})

useHead({
  htmlAttrs: {
    lang: 'en'
  },
  title: "Main Page",
  link: [
    {
      rel: 'icon',
      type: 'image/ico',
      href: '/favicon.ico'
    }
  ]
})

</script>
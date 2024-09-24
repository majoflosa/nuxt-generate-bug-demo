<script setup>
const { data } = await useAsyncData('test', () => queryContent('test').findOne());
</script>

<template>
  <div>
    <h1>Bug Demo: Nuxt Static Site Generation</h1>
    <p>When running 'npm run generate' or 'nuxt generate', the process breaks when pre-rendering json content that contains 'href' in a string. An example use case is if we have an encoded html string in said content, and wanted to render it in a template. Granted, it's generally not safe, but in a case where we are migrating or importing CMS content with rich text from another platform, this is very plausible.</p>
    <pre>{{ data }}</pre>
  </div>
</template>
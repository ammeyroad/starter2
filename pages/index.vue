<template>
  <div>
    <h1>{{ doc.title }}</h1>
    <p>{{ doc.description }}</p>
    <ContentRenderer :value="doc" />
  </div>
</template>

<script setup lang="ts">
const { data: doc } = await useAsyncData('homepage', () =>
  queryContent('/').findOne()
)
</script>
<template>
  <div>
    <!-- Should be highlight as incorrect -->
    <h1>{{ mountain?.value?.title }}</h1> 

    <p>{{ mountain?.description }}</p>
  </div>
</template>

<script lang="ts" setup>
// https://nuxt.com/docs/getting-started/data-fetching#client-only-fetching
const { data: mountain } = useFetch<{
  title: string;
  description: string;
}>('/api/mountains/everest', {
  pick: [
    'title', 'description'
  ]
})
</script>
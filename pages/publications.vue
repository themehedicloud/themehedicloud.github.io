<template>
  <main class="min-h-screen">
    <AppHeader class="mb-12" title="Publications" />
    <div class="space-y-12">
      <ul v-for="group in grouped" :key="group.year" class="space-y-8">
        <AppUsesHeader :title="group.year" />
        <AppUsesItem v-for="(item, id) in group.items" :key="id" :item="item" />
      </ul>
    </div>
  </main>
</template>

<script setup>
import publications from '~/data/publications'

const grouped = computed(() => {
  const byYear = {}
  for (const pub of publications) {
    if (!byYear[pub.year]) byYear[pub.year] = []
    byYear[pub.year].push(pub)
  }
  
  return Object.entries(byYear)
    .sort((a, b) => b[0] - a[0])
    .map(([year, items]) => ({ year, items }))
})

const description = "List of my publications over the years."
useSeoMeta({
  title: "Publications | TheMehediCloud",
  description,
});
</script>

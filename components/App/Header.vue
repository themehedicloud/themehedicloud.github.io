<template>
  <div>
    <h1
      class="text-2xl font-bold tracking-tight text-lightaccent dark:text-darkaccent"
    >
      {{ title }}
    </h1>
    <p
      v-if="description"
      class="mt-6 text-base text-gray-600 dark:text-gray-300">
      {{ description }}
    </p>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: false,
  },
});
</script>

<template>
  <li>
    <!-- <NuxtLink :to="item.url" class="group" target="_blank" external> -->
      <p
        class="font-semibold text-gray-700 dark:text-gray-300"
      >
        {{ item.title }}
      </p>
      <p class="text-sm text-gray-500">{{ item.authors }}</p>
      <p
        class="text-lightaccent dark:text-darkaccent"
      >
        {{ item.event }}
      </p>
    <!-- </NuxtLink> -->
  </li>
</template>

<script setup>
defineProps({
  item: Object,
  required: true,
});
</script>

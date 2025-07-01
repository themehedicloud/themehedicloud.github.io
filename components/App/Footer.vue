<template>
  <footer
    class="max-w-2xl mx-auto text-gray-400 dark:text-gray-600 text-sm text-center pb-8"
  >
    <br>
    <p>T h e M e h e d i C l o u d</p>
    <p>© {{ year }} All rights reserved</p>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>
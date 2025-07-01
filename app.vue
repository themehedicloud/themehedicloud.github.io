<template>
  <NuxtLoadingIndicator :color="loadingColor" />
  <AppNavbar />
  <div class="h-28"></div>
  <UContainer>
    <NuxtPage />
  </UContainer>
  <div class="h-20"></div>
  <AppFooter />
</template>

<script setup>
const colorMode = useColorMode();

const loadingColor = computed(() =>
  colorMode.value === 'dark' ? '#2abc89' : '#cb2a42'
);
</script>

<style>
.page-enter-active,
.page-leave-active {
  transition: all 0.2s;
}

.page-leave-to {
  opacity: 0;
  transform: translateY(-5px);
}

.page-enter-from {
  opacity: 0;
  transform: translateY(5px);
}
</style>

<script setup>
import { ref, onMounted, computed } from 'vue';

const colorMode = useColorMode();
const isMounted = ref(false);

onMounted(() => {
  isMounted.value = true;
});

const isDark = computed(() => colorMode.value === 'dark');
const nextThemeIcon = computed(() =>
  isDark.value ? 'solar:sun-2-outline' : 'solar:moon-outline'
);

function toggleTheme() {
  colorMode.preference = isDark.value ? 'light' : 'dark';
}
</script>

<template>
  <UTooltip text="Toggle theme" :ui="{ popper: { strategy: 'absolute' } }">
    <button
      class="relative px-3 py-4 flex items-center justify-center transition hover:text-lightaccent dark:hover:text-darkaccent"
      @click="toggleTheme"
    >
      <Icon
        v-if="isMounted"
        aria-hidden="true"
        :name="nextThemeIcon"
        class="w-5 h-5"
      />
      <span class="sr-only">Toggle theme</span>
    </button>
  </UTooltip>
</template>

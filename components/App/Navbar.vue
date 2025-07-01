<template>
  <div ref="headerRef" :style="styles" class="fixed top-0 w-full z-50">
    <nav class="mx-auto px-4 sm:px-6 lg:px-8 max-w-2xl">
      <ul
        class="flex items-center my-4 px-3 text-sm font-medium text-gray-800 rounded-full shadow-lg bg-white/90 shadow-gray-800/5 ring-1 backdrop-blur dark:bg-gray-800/90 dark:text-gray-200 dark:ring-white/20 ring-gray-900/5"
      >
        <li v-for="item in items" :key="item.path">
          <UTooltip
            :text="item.name"
            :ui="{ popper: { strategy: 'absolute' } }"
          >
            <ULink
              :to="item.path"
              class="relative px-3 py-4 flex items-center justify-center transition hover:text-lightaccent dark:hover:text-darkaccent"
              active-class="text-lightaccent dark:text-darkaccent"
            >
              <Icon aria-hidden="true" :name="item.icon" class="w-5 h-5 z-10" />
              <span
                v-if="$route.path === item.path || $route.path === item.path + '/'"
                class="absolute inset-x-1 -bottom-0.5 h-0.5 bg-gradient-to-r from-lightaccent/0 via-lightaccent/70 to-lightaccent/0 dark:from-darkaccent/0 dark:via-darkaccent/40 dark:to-darkaccent/0"
              ></span>
              <span
                v-if="$route.path === item.path || $route.path === item.path + '/'"
                class="absolute h-8 w-8 z-0 rounded-full bg-gray-100 dark:bg-white/10 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"
              ></span>
              <span class="sr-only">{{ item.name }}</span>
            </ULink>
          </UTooltip>
        </li>
        <li class="flex-1"></li>
        <li>
          <AppThemeToggle />
        </li>
      </ul>
    </nav>
  </div>
</template>

<script setup>
import { useFixedHeader } from 'vue-use-fixed-header'
const headerRef = ref(null);
const { styles } = useFixedHeader(headerRef);

const items = [
  { name: "Home", path: "/", icon: "solar:home-smile-outline" },
  {
    name: "News",
    path: "/news",
    icon: "streamline-plump:announcement-megaphone",
  },
  {
    name: "Publications",
    path: "/publications",
    icon: "carbon:catalog-publish",
  },
];
</script>

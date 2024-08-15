<template>
  <div
    class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1"
    id="navbar-sticky"
  >
    <ul
      class="flex flex-col p-4 md:p-0 mt-4 font-medium border border-gray-100 rounded-lg md:space-x-8 rtl:space-x-reverse md:flex-row md:mt-0 md:border-0"
    >
      <li v-for="link in links" :key="link.name">
        <router-link
          :to="link.path"
          :class="[
            'block py-2 px-3 rounded md:p-0',
            isActive(link.path)
              ? 'text-white bg-green-700 md:bg-transparent md:text-green-700 dark:text-green-500'
              : 'text-gray-900 hover:bg-gray-100 md:hover:bg-transparent md:hover:text-green-700 dark:hover:text-green-500 dark:text-white dark:hover:bg-gray-700 md:dark:hover:bg-transparent dark:border-gray-700',
          ]"
        >
          {{ link.name }}
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router';

const router = useRouter();

const links = [
  { name: 'Home', path: '/' },
  { name: 'About', path: '/about' },
  { name: 'Services', path: '/services' },
  { name: 'Portfolio', path: '/portfolio' },
];

const isActive = (path) => {
  return router.currentRoute.value.path === path;
};
</script>

<script setup lang="ts">

import { defineProps, defineEmits } from 'vue'

// Define the prop
const props = defineProps({
  isActive: {
    type: Boolean,
    required: true
  }
})

// Define the emit function
const emit = defineEmits(['update:isActive'])

// Method to toggle the boolean value and emit the event
const toggleActive = () => {
  console.log('hii')
  console.log(props.isActive)
  emit('update:isActive', !props.isActive)
}
</script>
<template>
  <div class="flex">
    <!-- Overlay -->
    <div v-if="isActive" @click="toggleActive" class="fixed inset-0 bg-gray-800 bg-opacity-50 dark:bg-opacity-80 z-30"></div>

    <!-- Drawer -->
    <div
      :class="isActive ? 'translate-x-0' : '-translate-x-full'"
      class="fixed top-0 left-0 h-full w-64 bg-white dark:bg-gray-900 shadow-lg transform transition-transform duration-300 ease-in-out z-40"
    >
      <div class="p-4">
        <h2 class="text-lg font-bold text-gray-900 dark:text-gray-100">Navigation</h2>
        <ul class="mt-4">
          <li class="mb-2">
            <a href="#" class="text-gray-700 dark:text-gray-300 hover:text-gray-900 dark:hover:text-gray-100">Home</a>
          </li>
          <li class="mb-2">
            <a href="#about" class="text-gray-700 dark:text-gray-300 hover:text-gray-900 dark:hover:text-gray-100">About</a>
          </li>
          <li class="mb-2">
            <a href="#services" class="text-gray-700 dark:text-gray-300 hover:text-gray-900 dark:hover:text-gray-100">Services</a>
          </li>
          <li class="mb-2">
            <a href="#portfolio" class="text-gray-700 dark:text-gray-300 hover:text-gray-900 dark:hover:text-gray-100">Portfolio</a>
          </li>
        </ul>
      </div>
    </div>

    <!-- Toggle Button -->
    <button @click="toggleActive" class="p-4 focus:outline-none z-50 md:hidden">
      <svg
        v-if="!isActive"
        class="w-6 h-6 text-gray-800 dark:text-gray-100"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
      </svg>
      <svg
        v-else
        class="w-6 h-6 text-gray-800 dark:text-gray-100"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
      </svg>
    </button>
  </div>
</template>

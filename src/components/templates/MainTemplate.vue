<script setup lang="ts">
import { ref } from 'vue';

defineProps<{
  title: string;
  footerText: string;
}>();

const isDarkMode = ref(false);

const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  document.documentElement.classList.toggle('dark', isDarkMode.value);
};
</script>

<template>
  <div :class="['min-h-screen flex flex-col', { 'dark': isDarkMode }]">
    <header class="bg-blue-500 text-white p-4">
      <div class="container mx-auto flex justify-between items-center">
        <h1 class="text-2xl font-bold">{{ title }}</h1>
        <button @click="toggleDarkMode" class="p-2 rounded-full bg-blue-600 hover:bg-blue-700 transition duration-200 ease-in-out">
          {{ isDarkMode ? '🌞' : '🌙' }}
        </button>
      </div>
    </header>

    <main class="flex-grow container mx-auto p-4">
      <slot></slot>
    </main>

    <footer class="bg-gray-200 dark:bg-gray-800 p-4 text-center">
      <p>{{ footerText }}</p>
    </footer>
  </div>
</template>
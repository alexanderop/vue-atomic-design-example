<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  type: 'primary' | 'secondary';
}>();

const emit = defineEmits<{
  (e: 'click', event: MouseEvent): void;
}>();

const buttonClasses = computed(() => {
  return props.type === 'primary'
    ? 'bg-blue-500 hover:bg-blue-600 text-white'
    : 'bg-gray-200 hover:bg-gray-300 text-gray-800';
});
</script>

<template>
  <button
    :class="[
      'px-4 py-2 rounded transition duration-200 ease-in-out focus:outline-none focus:ring-2 focus:ring-offset-2',
      buttonClasses,
    ]"
    @click="emit('click', $event)"
  >
    <slot></slot>
  </button>
</template>
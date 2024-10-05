<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  todo: {
    id: number;
    text: string;
    completed: boolean;
  };
}>();

const emit = defineEmits<{
  (e: 'toggle', id: number): void;
}>();

const itemClasses = computed(() => {
  return props.todo.completed
    ? 'bg-green-100 dark:bg-green-800'
    : 'bg-white dark:bg-gray-800';
});
</script>

<template>
  <div
    :class="[
      'flex items-center p-4 mb-2 rounded-lg shadow transition-colors duration-200 ease-in-out cursor-pointer',
      itemClasses,
    ]"
    @click="emit('toggle', todo.id)"
  >
    <input
      type="checkbox"
      :checked="todo.completed"
      class="mr-2 form-checkbox h-5 w-5 text-blue-600 transition duration-150 ease-in-out"
      @click.stop
    />
    <span :class="{ 'line-through': todo.completed }">{{ todo.text }}</span>
  </div>
</template>
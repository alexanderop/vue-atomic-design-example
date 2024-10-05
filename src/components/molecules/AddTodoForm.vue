<script setup lang="ts">
import { ref } from 'vue';
import Button from '../atoms/Button.vue';
import Input from '../atoms/Input.vue';

const emit = defineEmits<{
  (e: 'add-todo', text: string): void;
}>();

const newTodo = ref('');

const addTodo = () => {
  if (newTodo.value.trim()) {
    emit('add-todo', newTodo.value.trim());
    newTodo.value = '';
  }
};
</script>

<template>
  <form @submit.prevent="addTodo" class="flex space-x-2 mb-4">
    <Input v-model="newTodo" placeholder="Add a new todo..." class="flex-grow" />
    <Button type="primary" @click="addTodo">Add</Button>
  </form>
</template>
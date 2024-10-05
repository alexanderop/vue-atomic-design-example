<script setup lang="ts">
import { ref } from 'vue';
import AddTodoForm from '../molecules/AddTodoForm.vue';
import TodoItem from '../atoms/TodoItem.vue';

interface Todo {
  id: number;
  text: string;
  completed: boolean;
}

const todos = ref<Todo[]>([]);

const addTodo = (text: string) => {
  todos.value.push({
    id: Date.now(),
    text,
    completed: false,
  });
};

const toggleTodo = (id: number) => {
  const todo = todos.value.find(t => t.id === id);
  if (todo) {
    todo.completed = !todo.completed;
  }
};
</script>

<template>
  <div>
    <AddTodoForm @add-todo="addTodo" />
    <div class="space-y-2">
      <TodoItem
        v-for="todo in todos"
        :key="todo.id"
        :todo="todo"
        @toggle="toggleTodo"
      />
    </div>
  </div>
</template>
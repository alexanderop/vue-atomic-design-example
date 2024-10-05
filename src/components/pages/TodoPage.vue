<script setup lang="ts">
import MainTemplate from '../templates/MainTemplate.vue';
import TodoList from '../organisms/TodoList.vue';
</script>

<template>
  <MainTemplate title="Vue 3 Todo App" footerText="© 2023 Vue 3 Todo App">
    <TodoList />
  </MainTemplate>
</template>
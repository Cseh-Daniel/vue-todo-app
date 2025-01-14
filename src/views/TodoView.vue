<template>
  <div>
    <h1>Todo List</h1>

    <TodoList :elements="['alma', 'korte', 'Banon']" />
  </div>
</template>

<script setup>
import TodoList from '@/components/Todo/TodoList.vue';
</script>

<style lang="scss" scoped></style>

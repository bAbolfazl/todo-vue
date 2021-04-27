<template>
  <div class="todo-list">
    todo lsit
    <InputTodo @add-item="$emit('add-item', $event)" />
    <TodoItems :list="list" @delete-item="$emit('delete-item', $event)" />
  </div>
</template>

<script>
import InputTodo from "./InputTodo";
import TodoItems from "./TodoItems";

export default {
  name: "TodoList",
  components: { InputTodo, TodoItems },
  props: {
    list: Array,
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

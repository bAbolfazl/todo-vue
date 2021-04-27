<template>
  <div class="todo-items">
    <div
      v-for="({ title }, i) in list"
      :key="i"
      class="d-flex align-items-center justify-content-around"
    >
      <div>
        {{ title }}
      </div>
      <div @click="handleDelete(title)" class="bg-bg-danger">
        Delete
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItems",
  props: {
    list: Array,
  },

  methods: {
    handleDelete(title) {
      this.$emit('delete-item', title)
    },
  },
};
</script>

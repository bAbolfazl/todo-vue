<template>
  <div class="input-todo">
    <input
      @keydown.enter="addInput()"
      type="text"
      v-model="input"
      ref="input"
    />
    <button @click="addInput()">sumbit</button>
  </div>
</template>

<script>
export default {
  name: "InputTodo",
  data() {
    return {
      input: "",
    };
  },

  methods: {
    addInput() {
      if (!this.input) return;

      this.$emit("add-item", this.input);
      this.input = "";
    },
  },
};
</script>

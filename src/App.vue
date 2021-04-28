<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <TodoList
      :list="todoList"
      @add-item="handleAdd"
      @delete-item="handleDelete($event)"
    />
    <router-view />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TodoList from "./components/TodoList";

export default {
  name: "App",
  components: {
    // HelloWorld
    TodoList,
  },

  data() {
    return {
      todoList: [
        {
          title: "first one",
          checked: false,
        },
        {
          title: "second one",
          checked: false,
        },
      ],
    };
  },
  methods: {
    handleAdd(payload) {
      this.todoList.push({
        title: payload,
        checked: false,
      });
      // this.todoList = [...this.todoList, { title: valu, checked: false }];
    },
    handleDelete(title) {
      this.todoList = this.todoList.filter((item) => item.title !== title);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

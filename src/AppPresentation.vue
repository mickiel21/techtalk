<template>
  <div id="app">
    <ToDos
      v-bind:todoEntries="todoEntries"
      @delete-todo-event="deleteToDoItem"
    />
    <AddToDoButton @add-todo-event="addToDoItem" />
  </div>
</template>

<script>
import ToDos from "./components/ToDos";
import AddToDoButton from "./components/AddToDoButton";
import axios from "axios";
export default {
  name: "App",
  components: {
    ToDos,
    AddToDoButton,
  },
  data() {
    return {
      todoEntries: [],
    };
  },
  methods: {
    addToDoItem(newToDoItem) {
      this.todoEntries = [...this.todoEntries, newToDoItem];
    },
    deleteToDoItem(toDoId) {
      this.todoEntries = this.todoEntries.filter((item) => item.id !== toDoId);
    },
  },

  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=10")
      .then((res) => (this.todoEntries = res.data))
      .catch((error) => {
        return Promise.reject(error);
      });
  },
};
</script>
<style >
#app {
}
</style>
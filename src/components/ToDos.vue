<template>
  <div class="todo--list">
    <h1 class="todo">TODO LIST</h1>
    <ul>
      <li v-bind:key="item.id" v-for="item in todoEntries">
        <ToDoItem
          v-bind:todoItem="item"
          @delete-todo-event="$emit('delete-todo-event', item.id)"
        />
      </li>
    </ul>
  </div>
</template>
<script>
import ToDoItem from "./ToDoItem";

export default {
  name: "ToDos",
  components: {
    ToDoItem,
  },
  props: ["todoEntries"],
};
</script>

<style scoped>
.todo {
  text-align: center;
  background-color: red;
}
</style>
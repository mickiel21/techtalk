 <template>
  <div v-bind:class="{ completed: todoItem.completed }">
    <p @click="markComplete">{{ todoItem.title }}</p>
    <button @click="$emit('delete-todo-event', todoItem.id)">Delete</button>
  </div>
</template>

<script>
export default {
  name: "ToDoItem",
  components: {},
  props: ["todoItem"],
};
</script>
 <style>
.completed {
  text-decoration: line-through;
}
</style>
<template>
  <div class="container">
    <div class="card">
        <div class="card" v-for="todo in todos" v-bind:key="todo.id">
          <TodoItems v-bind:todo="todo" v-on:del-handle="$emit('del-handle',todo.id)"></TodoItems>
        </div>
      </div>
    </div>
</template>

<script>
import TodoItems from "./TodoItems";
export default {
  name: "Todos",
  props: ["todos"],
  components: {
    TodoItems,
  },
};
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  padding: 5px;
  margin: 10px;
}
</style>
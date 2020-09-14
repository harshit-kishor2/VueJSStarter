<template>
  <div>
      <div class="cardItem" v-bind:class="{'is-completed':todo.completed}">
        <input type="checkbox" v-on:change="changeHandle" v-bind:checked="todo.completed" />
        <h4 class="title">Title : {{todo.title}}</h4>
        <h4 class="status">Completed : {{todo.completed}}</h4>
        <button @click="$emit('del-handle',todo.id)">
          <font-awesome-icon style="color:darkred" icon="trash"></font-awesome-icon>
        </button>
      </div>
    </div>
  
</template>

<script>
export default {
  name: "TododItems",
  props: ["todo"],
  methods: {
    changeHandle() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.cardItem {
  display: flex;
  flex-direction: column;
  border: steelblue solid 2px;
  width: 200px;
  height: 200px;
  justify-content: center;
  align-items: center;
  background: lightcoral;
  color: darkblue;
}
.is-completed {
  background: lightgreen;
  color: darkblue;
}
</style>
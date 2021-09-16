<template>
  <div class="todo-list">
    <div class="todo-list-container">
      <form>
        <label for="todoitem">Task:</label>
        <input
          type="text"
          v-model="input"
          id="todoitem"
          placeholder="Add new task"
        />
        <button type="button" v-on:click.prevent="anadirElemento">Add</button>
      </form>
      <Items :todos="todos" @borrarItem="borrarElemento" />
    </div>
  </div>
</template>

<script>
import Items from "./components/items.vue";

export default {
  name: "App",
  components: {
    Items,
  },

  data() {
    return {
      todos: [],
    };
  },
  methods: {
    anadirElemento() {
      this.todos.push(this.input);
      this.input = "";
    },
    borrarElemento(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style>
.todo-list-container {
  display: flex;
  flex-flow: column nowrap;
  padding: 20px;
  align-items: center;
}
</style>

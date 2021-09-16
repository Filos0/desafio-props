<template>
  <div class="hello">
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todos[index] }}
        <button @click="borrarItem(index)">x</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "items",
  props: {
    todos: Array,
  },
  methods: {
    borrarItem(index) {
      this.$emit("borrarItem", index);
    },
  },
};
</script>

<style scoped>
button {
  color: red;
}
</style>

<template>
  <div>
    <ul>
      <todoitem v-for="todoVar of todosArray"
       v-bind:NameElement = "todoVar"
                v-on:remove-Element="removeElement"
      />
    </ul>
  </div>
</template>

<script>
import Todoitem from "./Todoitem";
export default {
name: "TodoList",
  props: ['todosArray'],
  components: {Todoitem},
  methods: {
    removeElement (id){ this.$emit('remove-Element', id)}
  }
}
</script>

<style scoped>
ul {list-style:none; margin:0; padding: 0;}
</style>
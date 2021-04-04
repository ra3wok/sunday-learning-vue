<template>
  <div id="app">
    <h1>My sunday vue app</h1>
</hr>
    <TodoList
    v-bind:todosArray="todos"
    @remove-Element = "removeElement"
    />
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
export default {
  name: 'App',
  data () {
    return {
      todos:[
        {id: 1, title: "Сходить в магаз", completed: false},
        {id: 3, title: "Сделать зарядку", completed: false},
        {id: 4, title: "Сходить в парикмахерскую", completed: false}

      ]
    }
    },
  methods: {
    removeElement (id){
      this.todos = this.todos.filter(todoVar => todoVar.id !== id)
}
  },
  components: {
    TodoList
  }
}
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

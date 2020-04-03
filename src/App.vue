<template>
  <div id="app">
    <AddTodo @add-todo="addTodo"/>
    <Todos v-bind:todos="todos"/>
  </div>
</template>

<script>
import AddTodo from './components/Todos/AddTodo.vue'
import Todos from './components/Todos/Todos.vue'

export default {
  name: 'App',
  components: {
    AddTodo,
    Todos
  },
  data(){
    return{
      todos: [
        {
          id: 1,
          title: "todo one",
          completed: false
        },
        {
          id: 2,
          title: "todo two",
          completed: true
        },
        {
          id: 3,
          title: "todo three",
          completed: false
        }
      ]
    }
  },
  methods: {
    addTodo(todo){
      this.todos.unshift(todo)
      alert("提交成功！");
    }
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

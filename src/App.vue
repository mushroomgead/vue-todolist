<template>
  <AddTodo @addTodo="addTodos" />
  <ItemList :todolist="todos" @removeTodo="removeTodoList" @checkTodo="checkTodoList"/>
</template>

<script>
import AddTodo from './components/AddTodo.vue'
import ItemList from './components/ItemList.vue'

export default {
  name: 'App',
  components: {
    AddTodo,
    ItemList
  },
  props: ['todolist'],
  data() {
    return {
      todos: []
    }
  },
  methods: {
    addTodos(value) {
      this.todos.push(value)
    },
    removeTodoList(key) {
      this.todos = this.todos.filter((_, index) => index !== key)
    },
    checkTodoList(key) {
      this.todos[key].checked = !this.todos[key].checked
    }
  },
}
</script>

<style>

</style>

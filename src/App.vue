<template>
<b-container class="bv-example-row">
    <b-row cols="6" cols-sm="12" cols-md="8" cols-lg="6">
		<div class="app-todo">
        <h1>todo list</h1>
        <AddTodo 
          v-on:add-todo="addTodo"
        />
        <TodoList 
          v-bind:todos="todos"
          v-on:remove-todo="removeTodo"
        />
		</div>
    </b-row>
</b-container>
</template>

<script>
import TodoList from '@/components/TodoList'
import AddTodo from '@/components/AddTodo'

export default {
  name: 'app',
  data() {
    return {
      todos: [
        {id: 1, title: 'buy apple', completed: false},
        {id: 2, title: 'buy orange', completed: false},
        {id: 3, title: 'buy tomato', completed: false}
      ]
    }
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo(todo) {
      this.todos.push(todo)
    }
  },
  components: {
    TodoList,
    AddTodo
  }
}
</script>

<style scoped>
    .app-todo {
		min-width: 100%;
	}
</style>
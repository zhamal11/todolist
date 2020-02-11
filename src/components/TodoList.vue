<template>
    <b-list-group>
		<TodoItem
				v-for="(todo, idx) of todos"
				v-bind:todo="todo"
				v-bind:index="idx"
				v-on:remove-todo="removeTodo"
			/>
	</b-list-group>
</template>

<script>
import TodoItem from '@/components/TodoItem'

export default {
	props: ['todos'],
	components: {
		TodoItem
	},
	methods: {
		removeTodo(id) {
			this.$emit('remove-todo', id)
		}
	}
}
</script>

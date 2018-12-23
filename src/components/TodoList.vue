<template>
	<div>
	<p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
	<!-- <my-component v-for="(item, index) in items" v-bind:item="item"  v-bind:index="index">
</my-component> -->
<!-- //v-on delete taken from todo.vue -->
	<todo v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo" v-for="todo in todos" v-bind:todo="todo">
		
	</todo>
</div>
</template>

<script>
import todo from './Todo.vue';
export default{
	//passing data from root component to the child component use prop
	components:{
		todo
	},
	//Rendering the prop from TodoList.vue

	props:['todos'],
	data () {
    	return {
      		
    	}
  	},
  	methods:{
  		deleteTodo(todo) {
      		const todoIndex = this.todos.indexOf(todo);
      		this.todos.splice(todoIndex, 1);
    	},
    	completeTodo(todo) {
      		const todoIndex = this.todos.indexOf(todo);
      		this.todos[todoIndex].done = true;
    	}
  	}
}
</script>
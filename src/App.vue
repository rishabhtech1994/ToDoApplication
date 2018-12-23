<template>
  <div id="app">
    <div>
    <ToDoList v-bind:todos="todos">
    </ToDoList>
    <CreateTodo >
    </CreateTodo v-on:create-todo="addTodo">
  </div>
    <router-view/>
  </div>
</template>

<script>

//import demoVue from './components/MyVue.vue';
import ToDoList from './components/TodoList.vue';
import CreateTodo from './components/CreateTodo.vue';

export default{
  //props:['todos'],
  components:{
    ToDoList,
    CreateTodo
  },
  data () {
      return {
          todos:[
            {
              title:'Todo A',
              project:'Project A',
              done:'false',

            },{
              title:'Todo B',
              project:'Project B',
              done:'true',

            },{
              title:'Todo C',
              project:'Project C',
              done:'false',

            }]
      }
    },
    methods:{
      addTodo:function(title){
        this.todos.push({
          title,
          done:false
        });

      }
    },
  name: 'App'
}
</script>

<style>

</style>

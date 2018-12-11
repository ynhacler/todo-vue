<template>
  <div>
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:add-todo="addTodo"></create-todo>
  </div>
</template>

<script>
import TodoList from './components/TodoList'
import CreateTodo from './components/CreateTodo'

export default {
  components:{
    TodoList,
    CreateTodo,
  },
  data(){
    return {
      todos:[
        {
          title:'Todo A',
          project:'Project A',
          done:false
        },
        {
          title:'Todo B',
          project:'Project B',
          done:true
        },
        {
          title:'Todo C',
          project:'Project C',
          done:false
        },
        {
          title:'Todo D',
          project:'Project D',
          done:true
        },
      ],
    };
  },
  methods:{
    addTodo(title){
      this.todos.push(
        {
          title,
          done:false,
        }
      );
    },
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:red;
  margin-top: 60px;
}
</style>

<template>
 <div id="app">
   <Header />
   <AddTodo  v-on:add-todo="addTodo" />
  <Todos  v-bind:todos="todos"   v-on:del-todo="deleteTodo" />
 </div>
</template>

<script>
import Header from './components/layout/header';
import AddTodo from './components/AddTodo';
import Todos from './components/Todos';

export default {
  name: 'App',
  components: {
    Header,
    AddTodo,
    Todos
  },
 
  data() {
    return {
      todos:[
        {
          id:1,
          title:"Todo One",
          completed:false
        },
         {
          id:2,
          title:"Todo Two",
          completed:true
        },
         {
          id:3,
          title:"Todo Three",
          completed:false
        }
      ]
    }
  },

  methods:{
    deleteTodo(id){
     this.todos = this.todos.filter(todo => todo.id !==id)
    }
  },
  addTodo(newTodo){
    this.todos = [...this.todos, newTodo];
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
  padding: 3px;
}

.btn{
  display: inline-block;
  border: none;
  background: #5555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover{
  background:#666;
}
</style>

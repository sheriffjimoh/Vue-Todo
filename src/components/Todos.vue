<template>
    <div v-for="todo in todos"  :key="todo.id" >
      <TodoItem v-bind:todo="todo"  v-on:del-todo="$emit('del-todo', todo.id)"/>
    </div>
</template>

<script>
import TodoItem from './Todoitem.vue';
export default {
    name:"Todos",
    props:["todos"],
    components:{
        TodoItem
    }
}
</script>

<style scoped>

</style>
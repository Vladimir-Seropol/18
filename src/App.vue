

<template>

  <div id="app">
   <TodoList  />

  
      <TaskItem />
  


   
  </div>
</template>


<script>
import TaskItem from './components/TaskItem.vue';
import TodoList from './components/TodoList.vue';

export default {

    data() {
    return {
      tasks: [], 
      newTaskText: '',
      nextId: 1
    };
  },
  components: {
    TodoList,

    TaskItem,
  },
  
  };


</script>


<style>



</style>

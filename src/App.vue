

<template>

  <div id="app">
   <TodoList  />
<TaskItem  :task="task"/>
  


   
  </div>
</template>


<script>
import TaskItem from './components/TaskItem.vue';
import TodoList from './components/TodoList.vue';

export default {


  components: {
    TodoList,

    TaskItem,
  },
  
  };


</script>


<style>



</style>

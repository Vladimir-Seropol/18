

<template>

  <div id="container">
   <TodoList  />
<TaskItem  />
  


   
  </div>
</template>


<script setup>

import TodoList from './components/TodoList.vue';

</script>


<style scoped>

.container {
    width: 300px;
    height: auto;
    
}
</style>

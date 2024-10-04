<template>
    <ol>
        <li :class="{ completed: task.completed }">
           <span>{{ task.text }}</span>
           <div class="button">
            <button @click="toggleCompletion(task)">✔️</button>
           <button @click="deleteTask(task.id)">❌</button>
           </div>
           
         </li>
    </ol>
   </template>
   
   <script>
   export default {
       props: {
           task: {
               type: Object,
               required: true
           }
       },
       methods: {
           deleteTask(id) {
               this.$emit('del', id);
           },
           toggleCompletion(task) {
               this.$emit('toggle', task);
           }
       }
   };
   </script>
   
   <style scoped>
   li{
    margin: 10px;
   }
   .completed {
    text-decoration: line-through;
    color: gray;
    background-color: #f0f0f0;
   }

 
   li{
    display: flex;
    justify-content: space-between;
    width: 300px;
    border-bottom: 1px solid wheat;
   }
   button{
    margin-right: 5px;
   }
   </style>
<template>
 
 <div v-for="task in tasks" :key="task.id">
        <span :class="{ completed: task.completed }">{{ task.text }}</span>
        <button @click="toggleCompletion(task)">✔️</button>
        <button @click="removeTask(task.id)">❌</button>
      </div>
        
  


</template>


<script>
// import TodoList from './TodoList.vue';

export default {
    // name: 'TaskItem',
    // props: ['task', 'text', 'id'],
    props: {
    task: {
      type: Object,
      required: true
    }
  },
   
methods: {
    removeTask(id) {
        // this.tasks = this.tasks.filter(task => task.id !== id);
        this.$emit('remove', this.task.id);
      },
      toggleCompletion(task) {
        // task.completed = !task.completed;
        this.$emit('toggle', task);

        
      }
}
}
</script>

<style>
.completed {
            text-decoration: line-through;
            color: gray;
}
</style>
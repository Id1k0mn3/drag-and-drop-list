<template>
  <div
    class="section-drag"  
    v-on:dragover="allowDrop" 
    v-on:drop="drop">
    
    <h2>block</h2>
    <button @click="addTask">add task</button>
    <task-item 
      v-for="task in arrayTasks"
      :key="task"
      :id="task" 
      @dragstart="dragStart"
      draggable="true"></task-item>
  </div>
</template>

<script>

import TaskItem from './TaskItem.vue';

export default {
  components: {
    TaskItem
  },
  data() {
    return {
      arrayTasks: [],
    }
  },
  methods: {
    addTask() {
      this.arrayTasks.push(Math.random())
    },
    dragStart:function(event)  {
      event.dataTransfer.setData("Text", event.target.id);
    },
    allowDrop:function(event) {
      event.preventDefault();
    },
    drop:function(event) {
      event.preventDefault();
      var data = event.dataTransfer.getData("Text");
      event.target.appendChild(document.getElementById(data));
    },
  }
}
</script>

<style scoped>
  .section-drag {
    padding: 20px;
    border: 1px solid red;
    margin: 10px
  }
</style>
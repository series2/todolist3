<template>
  <div>
    <div>ToDoList</div>
     <div>unfinished</div>
        <div v-for="task in tasks" :key="task.name">
     
        <div class="name">名前: {{ task.name }} 
            <button @click="endTask">end</button></div>

    </div>

    <div>finished</div>
    
     <div>
      <label>
        名前
        <input type="text" v-model="newTaskName">
      </label>
      <button @click="addTask">add</button>
    </div>
  </div>
  
  
</template>

<script>
export default {
  
  name: "TaskList",
  data() {
    return {
      tasks: [{ name: "たまご"}, { name: "りんご"}],
      newTaskName: "",
    };
  },
  
  methods: {
    addTask() {
      this.tasks.push({ name: this.newTaskName});
    }
  }

};
</script>

<style>
.over500 {
  color: red;
}
</style>
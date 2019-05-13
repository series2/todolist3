<template>
  <div>
    <div>ToDoList</div>
    <div v-for="task in tasks" :key="task.name">
      <div class="task" :class="{over500: task.price >= 500}">
        <div class="name">名前: {{ task.name }}</div>
        <div class="price">{{ task.price }} 円</div>
        <div v-if="task.price >= 10000">高額商品</div>
      </div>
    </div>
     <div>
      <label>
        名前
        <input type="text" v-model="newTaskName">
      </label>
      <label>
        価格
        <input type="number" v-model="newTaskPrice">
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
      tasks: [{ name: "たまご", price: 100 }, { name: "りんご", price: 160 }],
      newTaskName: "",
      newTaskPrice: 0
    };
  },
  methods: {
    addTask() {
      this.tasks.push({ name: this.newTaskName, price: this.newTaskPrice });
    }
  }
};
</script>

<style>
.over500 {
  color: red;
}
</style>
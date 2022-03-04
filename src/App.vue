<template>
  <div id="app">
    <BaseHeader/>
    <main>
      <TaskCard v-for="task in tasks" :key="task.id" :task="task" @change-task-state="changeTaskDone"/>

    </main>
  </div>
</template>

<script>
import BaseHeader from "@/components/BaseHeader";
import TaskCard from "@/components/TaskCard";

export default {
  name: 'App',
  components: {
    BaseHeader,
    TaskCard
  },
  data() {
    return {
      tasks: [
        {
          id: 0,
          name: 'Купить хлеб',
          done: false
        },
        {
          id: 1,
          name: 'Купить сыра',
          done: false
        },
        {
          id: 2,
          name: 'Купить пива',
          done: false
        }
      ]
    }
  },
  methods: {
    changeTaskDone(task_id) {
      this.tasks[this.tasks.findIndex(item => item.id == task_id)].done = !this.tasks[this.tasks.findIndex(item => item.id == task_id)].done
    }
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
}
</style>

<template>
<div class="task-card">
  <h2>{{task.name}}</h2>
  <input type="checkbox" @change="changeTaskDone" >
</div>
</template>

<script>
export default {
  name: "TaskCard",
  props:{
    task:   Object,
  },
  methods:{
    changeTaskDone(){
      this.$emit('change-task-state', this.task.id)
    }
  }
}
</script>

<style scoped>
.task-card{
  background-color: bisque;
  width: 200px;
  margin: 0 auto;
}
</style>
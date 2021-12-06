<template>
  <div :key="task.id" v-for="task in tasks">
    <Task
      @toggle="$emit('toggle', task.id)"
      :task="task"
      @delete-task="$emit('delete', task.id)"
    ></Task>
  </div>
</template>
<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  props: ["tasks"],
  components: {
    Task,
  },
  emits: ["delete", "toggle"],
};
</script>

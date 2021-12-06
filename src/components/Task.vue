<template>
  <div
    @dblclick="$emit('toggle', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }} <i @click="onDelete(task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>
<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods: {
    onDelete(id) {
      this.$emit("delete-task", id);
    },
  },
  emits: ["toggle"],
};
</script>
<style scope>
.fas {
  color: rgb(11, 165, 204);
}
.task {
  background: rgb(6, 72, 88);
  margin: 5px;
  color: beige;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid rgb(11, 165, 204);
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 10px;
}
</style>

<template>
  <header>
    <h1>{{ title }}</h1>
    <Button @toggle-form="toggleForm" text="add task" color="tomato" />
  </header>
</template>
<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  props: {
    title: {
      type: String,
      default: "ok",
    },
  },
  components: {
    Button,
  },
  methods: {
    toggleForm() {
      this.$emit("toggleForm");
    },
  },
};
</script>
<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>

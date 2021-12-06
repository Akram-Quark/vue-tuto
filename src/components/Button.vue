<template>
  <button @click="onClick()" :style="{ background: color }" class="btn">
    {{ text }}
  </button>
</template>
<script>
export default {
  name: "Button",
  props: ["text", "color"],
  methods: {
    onClick() {
      alert("Click");
    },
  },
};
</script>
<style scoped></style>

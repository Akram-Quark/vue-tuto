<template>
  <div class="container">
    <Header title="task manager" />
    <Tasks @toggle="toggleRemind" @delete="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
export default {
  name: "App",
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    deleteTask(id) {
      if (confirm("are you sur ?")) {
        this.tasks = this.tasks.filter((t) => t.id !== id);
      }
    },
    toggleRemind(id) {
      this.tasks = this.tasks.map((t) =>
        t.id === id ? { ...t, reminder: !t.reminder } : { ...t },
      );
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "do something",
        day: "2 march at 12:00",
        reminder: true,
      },
      { id: 2, text: "go foreward", day: "3 may at 1:00", reminder: true },
      {
        id: 3,
        text: "believe in you",
        day: "6 jun at 22:00",
        reminder: false,
      },
    ];
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "roboto", sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>

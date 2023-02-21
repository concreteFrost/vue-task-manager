<template>
  <div class="container">
    <Header title="Task Tracker v 1.0"></Header>
    <Body :tasks="tasks" @delete-task ="deleteTask" @toggle-reminder="toggleReminder" ></Body>
  </div>
</template>

<script>
import Header from "./components/Header/Header.vue";
import Body from "./components/Body/Body.vue";

export default {
  name: "App",
  components: {
    Header,
    Body,
  },
  data() {
    return { tasks: Object };
  },
  methods:{
    deleteTask(id){
      this.tasks = this.tasks.filter((e)=>e.id !== id)
    },
    toggleReminder(id){
      this.tasks = this.tasks.map((task) => ({
    ...task,
    reminder: task.id === id ? !task.reminder : task.reminder,
  }));
    }
  },
  created() {
    this.tasks = [
      {
        id: 0,
        content: "Play Guitars",
        reminder:true,
      },
      {
        id:1,
        content: "Eat Food",
        reminder: false
      },
      {
        id:2,
        content: "Go to Bed",
        reminder:true
      },
    ];
  },
};
</script>

<style scoped lang="scss">
@import "./App.module.scss";
</style>

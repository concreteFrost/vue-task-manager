<template>
  <div class="container">
    <div class="button_container">
      <ManageTaskButton content="Add Task"></ManageTaskButton>
      <ManageTaskButton content="Edit Task"></ManageTaskButton>
      <ManageTaskButton content="Remove Task"></ManageTaskButton>
    </div>
    <Tasks :tasks="tasks" @delete-task ="deleteTask"></Tasks>
  </div>
</template>

<script>
import ManageTaskButton from "./ManageTaskButton/ManageTaskButton.vue";
import Tasks from "./Tasks/Tasks.vue";

export default {
  name: "PageBody",
  components: { ManageTaskButton, Tasks},
  props:{tasks:Object},
  methods:{
    deleteTask(id){
      this.$emit('delete-task',id);
    }
  }
};
</script>

<style scoped lang="scss">
@import "./Body.module.scss";
</style>

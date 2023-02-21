<template>
  <div :key="task.id" v-for="task in tasks">
    <div :class="[task.reminder == true ? 'reminder' : 'task']">
      <div class="task_item">
        <p>{{ task.content }}</p>
      </div>
      <div class="task_action">
        <button @click="$emit('delete-task',task.id)">Delete</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PageTasks",
  props: {
    tasks: Array,
  },
  emits:
    ['delete-task']

};
</script>

<style lang="scss">
@import "./Tasks.module.scss";
</style>

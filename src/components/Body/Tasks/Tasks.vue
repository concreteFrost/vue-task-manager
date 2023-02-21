<template>
  <div :key="task.id" v-for="task in tasks">
    <div :class="[task.reminder == true ? 'reminder' : 'task']">
      <div class="task_item">
        <p @click="$emit('toggle-reminder',task.id)">{{ task.content }}</p>
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
  methods:{
    alertFunc(){
      alert('jio')
    }
  },
  emits:
    ['delete-task','toggle-reminder']

};
</script>

<style lang="scss">
@import "./Tasks.module.scss";
</style>

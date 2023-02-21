<template>
  <div>
    <button class="task_button" :style="{ background: color }" @click="addTask">
      {{ content }}
    </button>
  </div>
</template>

<script>
export default {
  name: "PageManageTaskButton",
  props: {
    content: String,
    color: {
      type: String,
      default: "black",
    },
  },
  methods: {
    addTask() {
      alert("click");
    },
  },
};
</script>

<style scoped lang="scss">
@import "./ManageTaskButton.module.scss";
</style>

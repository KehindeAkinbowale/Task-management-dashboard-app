<template>
  <div class="task-list--container">
    <p>{{ id }}</p>
    <p style="width: 25%">{{ title }}</p>
    <p>{{ description }}</p>
    <p>{{ dueDate }}</p>
    <p>Pending</p>
    <p style="cursor: pointer" @click="editTask">Edit</p>
  </div>
</template>

<script setup lang="ts">
const props = defineProps<{
  id: string;
  title: string;
  description: string;
  dueDate;
}>();

const emits = defineEmits(["edit-task"]);
const editTask = () => {
  emits("edit-task", props);
  console.log("edit task");
};
</script>

<style scoped>
.task-list--container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}
.task-list--container p {
  width: 25%;
  text-align: center;
}

@media only screen and (max-width: 1024px) {
  .task-list--container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }
  .task-list--container p {
    width: 25%;
    text-align: center;
    font-size: 12px;
  }
}
</style>

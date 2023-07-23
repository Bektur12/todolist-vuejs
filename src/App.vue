<template>
  <main>
    <TaskInput></TaskInput>
    <TaskCard></TaskCard>
  </main>
</template>

<script>
import TaskCard from "./components/TaskCard.vue";
import TaskInput from "./components/TaskInput.vue";

export default {
  name: "App",
  components: {
    TaskCard,
    TaskInput,
  },
};
</script>

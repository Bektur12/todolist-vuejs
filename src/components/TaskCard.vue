<template>
  <div class="task-card my-style">
    <div>
      <h4>{{ model.title }}</h4>
      <p>{{ model.description }}</p>
    </div>
    <div>
      <button @click="emitOnDone" v-if="!model.status">add</button>
      <button @click="emitOnRemove" v-else>delete</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    model: {
      required: true,
      default: {
        id: 0,
        title: "CreateVideo",
        description: "And upload on YouTube",
        status: false,
      },
    },
  },
  setup(props, { emit }) {
    const emitOnDone = () => {
      emit("onDone");
    };
    const emitOnRemove = () => {
      emit("onRemove");
    };

    return {
      emitOnDone,
      emitOnRemove,
    };
  },
};
</script>

<style scoped>
.task-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>

<template>
  <div>
    <TaskInput></TaskInput>
    <b-container>
      <div v-for="(item, index) in listItems" :key="index">
        <Task
          v-bind:task="{item}"
        ></Task>
      </div>
      <div v-for="(item, index) in finishedItems" :key="'a' + index">
        <Task
          v-bind:task="{item}"
        ></Task>
      </div>
    </b-container>
  </div>
</template>

<script>
import Task from "./Task.vue";
import TaskInput from "./TaskInput.vue";
export default {
  components: {
    Task,
    TaskInput,
  },
  computed: {
    listItems() {
      return this.$store.state.listItems;
    },
    finishedItems() {
      return this.$store.state.finishedItems;
    },
  },
  methods: {

  },
};
</script>

<style >
</style>
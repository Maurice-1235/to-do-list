<template>
  <div>
    <input
      v-model="inputtext"
      v-on:keydown.enter="addTask"
      type="text"
      class="tasklistinput"
      placeholder="Insert your task here..."
    />
    <b-container>
      <div v-for="(item, index) in taskmodel" :key="index">
        <Task v-bind:task="{item}"></Task>
      </div>
    </b-container>
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  components: {
    Task
  },
  data() {
    return {
      inputtext: "",
      taskmodel: []
    };
  },
  methods: {
    addTask: function() {
      this.taskmodel.push({ taskname: this.inputtext, taskchecked: false });
      this.inputtext = "";
    }
  }
};
</script>

<style >
.tasklistinput {
  background-color: rgb(49, 49, 49);
  color: white;
  font-size: 20px;
  margin-top: 20px;
  width: 100%;
  padding: 10px 20px;
  border: 1px rgb(31, 31, 31) solid;
  border-radius: 10px;

  -webkit-box-shadow: 0px 0px 5px 0px rgb(31, 31, 31);
  -moz-box-shadow: 0px 0px 5px 0px rgb(31, 31, 31);
  box-shadow: 0px 0px 5px 0px rgb(31, 31, 31);

  /* transition: box-shadow .5s; */
}
.tasklistinput:focus {
  outline: none;
}
</style>
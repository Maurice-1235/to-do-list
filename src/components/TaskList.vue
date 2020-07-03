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
        <Task v-bind:task="{item}" @moveToTaskdone="moveToTaskdone" @movetoTaskmodel="moveToTaskmodel"></Task>
      </div>
      <div v-for="(item, index) in taskdone" :key="'a' + index">
        <Task v-bind:task="{item}" @moveToTaskdone="moveToTaskdone" @movetoTaskmodel="moveToTaskmodel"></Task>
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
      taskmodel: [],
      taskdone: []
    };
  },
  methods: {
    addTask: function() {
      this.taskmodel.push({ taskname: this.inputtext, taskchecked: false });
      this.inputtext = "";
    },
    moveToTaskdone: function(item) {
      this.taskdone.push({ taskname: item[0], taskchecked: true });
      this.removeItemFromListByName(item[0], this.taskmodel);
    },
    moveToTaskmodel: function(item) {
      console.log("moveback");
      this.taskmodel.push({ taskname: item[0], taskchecked: false });
      this.removeItemFromListByName(item[0], this.taskdone);
    },
    removeItemFromListByName(itemname, itemlist) {
      itemlist.forEach(function(item) {
        if (item.taskname == itemname) {
          itemlist.splice(itemlist.indexOf(item), 1);
        }
      });
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
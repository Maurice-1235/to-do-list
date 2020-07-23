<template>
  <b-row class="taskcontainer" v-bind:class="{checked : task.item.taskchecked}">
    <b-col cols="1">
      <!-- <input type="checkbox" class="taskcheck" v-model="task.item.taskchecked" v-on:click="sortTaskModel(task.item)" /> -->
      <input type="checkbox" class="taskcheck" v-model="task.item.taskchecked" v-on:click="sortTaskModel(task.item)" />
    </b-col>
    <b-col cols="11">{{task.item.taskname}}</b-col>
  </b-row>
</template>

<script>
export default {
  props: {
    task: Object
  },
  methods: {
    sortTaskModel: function(item) {
      if (!item.taskchecked) {
        // console.log('moveToTaskdone');
        this.$emit('moveToTaskdone', [item.taskname, item.taskchecked]);
      } else {
        this.$emit('moveToTaskmodel', [item.taskname, item.taskchecked]);
      }
    }
  },
};
</script>
<style scoped>
.taskcheck {
  scale: 150%;
}
.taskcontainer {
  background-color: rgb(34, 34, 34);
  color: rgb(228, 228, 228);
  margin-top: 20px;
  padding: 10px;
  font-size: 20px;
  border: 1px rgb(46, 46, 46) solid;
  border-radius: 10px;

  -webkit-box-shadow: 0px 0px 5px 0px rgb(31, 31, 31);
  -moz-box-shadow: 0px 0px 5px 0px rgb(31, 31, 31);
  box-shadow: 0px 0px 5px 0px rgb(31, 31, 31);
}
.checked {
  background-color: rgb(61, 151, 73);
  /* color: rgb(128, 128, 128); */
  text-decoration: line-through;
}
</style>
<template>
  <b-row class="taskcontainer">
    <b-col cols="1">
      <input type="checkbox" class="taskcheck" :checked="task.item.taskchecked" />
    </b-col>
    <b-col cols="11">{{task.item.taskname}}</b-col>
  </b-row>
</template>

<script>
export default {
  props: {
    task: Object
  }
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
</style>
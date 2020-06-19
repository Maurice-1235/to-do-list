<template>
  <b-container>
    <b-row>
      <b-col>
        <TaskList></TaskList>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";
import TaskList from "./components/TaskList.vue";
export default {
  components: {
    TaskList
  }
};
</script>

<style>
body{
  background-color: rgb(49, 49, 49);
}
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>

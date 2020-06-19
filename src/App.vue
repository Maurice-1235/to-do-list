<template>
  <div id="list" v-bind:disable="checked">
    <b-row>
      <b-col>
        <input class="checkmark" type="checkbox" v-model="checked" />
      </b-col>
      <b-col>
        <b-row>
          <!-- <TaskInput v-on:eventInput="number=$event"></TaskInput> -->
        </b-row>
        <b-row>
        <TaskList></TaskList>
        <div class="button" variant="primary" v-on:click="edit">
          <b-icon icon="pencil">pencil</b-icon>
        </div>
        <div class="button" variant="danger" v-on:click="deleteI">
          <b-icon icon="trash"></b-icon>
        </div>
        </b-row>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";
import TaskList from './components/TaskList.vue'
// import TaskInput from './components/TaskInput.vue'
export default {
  components: { 
   TaskList,
  //  TaskInput
   },
  data(){
    return{
      content:"Halo",
      checked:false,
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

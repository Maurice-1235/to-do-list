<template>
  <div>
    <input v-model="inputItem" v-on:keydown.enter="addTask" class="tasklistinput" type="text" />
  </div>
</template>

<script>
export default {
  computed: {
    listItems() {
      return this.$store.state.listItems;
    },
  },
  data() {
    return {
      inputItem: "",
    };
  },
  methods: {
    addTask() {
      this.listItems.push({text: this.inputItem, checked: false });
      this.inputItem = "";
    },
  },
};
</script>

<style scoped>
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
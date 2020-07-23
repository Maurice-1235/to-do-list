<template>
  <b-row class="taskcontainer" v-bind:class="{checked : task.item.checked}">
    <b-col cols="1">
      <input
        type="checkbox"
        class="taskcheck"
        v-model="task.item.checked"
        v-on:click="sortTaskModel(task.item, $event)"
      />
    </b-col>
    <b-col cols="11">{{task.item.text}}</b-col>
  </b-row>
</template>

<script>
export default {
  props: {
    task: Object,
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
    sortTaskModel: function (item, event) {
      event.preventDefault();
      if (!item.checked) {
        this.finishedItems.push({ text: this.task.item.text, checked: true });
        this.removeItemFromListByName(this.task.item.text, this.listItems);
      } else {
        this.listItems.push({ text: this.task.item.text, checked: false });
        this.removeItemFromListByName(this.task.item.text, this.finishedItems);
      }
    },
    removeItemFromListByName(itemname, itemlist) {
      itemlist.forEach(function (item) {
        if (item.text == itemname) {
          itemlist.splice(itemlist.indexOf(item), 1);
        }
      });
    },
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
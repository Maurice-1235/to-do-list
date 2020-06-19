<template>
    <div>
     <input v-model="text" v-on:keydown.enter="addTask" type="text" />
     <!-- <button v-on:click="addTask"></button> -->
     <div v-for="(item, index) in data" :key="index">
         <Task v-bind:task="{item}"></Task>
     </div>
    </div>
</template>

<script>
    // import TaskInput from './TaskInput.vue'
    import Task from './Task.vue'
    export default {
        components: {
            // TaskInput,
            Task,
        },
        data() {
            return {
                text:0,
                data:[
                    {task:"makan",check:false},
                    {task:"minum",check:false},
                    {task:"tidur",check:true},
                    {task:"belajar",check:true},
                ]
            }
        },
        methods:{
            addTask:function(){
              this.data.push({ task: this.text, checked: false });
            }
        }
    }
</script>

<style >

</style>
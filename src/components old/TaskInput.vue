<template>
    <div>
       <input v-model="task" v-on:input="$emit('eventInput',taskname)" type="text" />
    </div>
</template>

<script>
    export default {
         data() {
            return {
                task:0
            }
        },
    }
</script>

<style >

</style>
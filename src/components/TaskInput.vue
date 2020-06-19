<template>
    <div>
       <input v-model="text" v-on:input="$emit('eventInput',text)" type="text" />
    </div>
</template>

<script>
    export default {
         data() {
            return {
                text:0
            }
        },
    }
</script>

<style >

</style>
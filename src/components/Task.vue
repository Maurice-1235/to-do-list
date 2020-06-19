<template>
    <div>
         <input type="checkbox" :checked="task.item.check">
         {{task.item.task}}
    </div>
</template>

<script>
    export default {
        props: {
            task:Object
            
        },
    }
</script>
<style scoped>

</style>
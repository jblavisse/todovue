<template>
    <div class="task">
       {{id}} {{title}}
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        id: Number,
        title: String
    }
}
</script>

<style>
.task {
    color: red;
}
</style>
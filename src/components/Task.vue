<template>
    <div class="task">
        {{title}}
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        title: String
    }
}
</script>

<style>
.task {
    color: red;
}
</style>
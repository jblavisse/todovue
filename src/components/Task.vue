<template>
    <!-- <div class="task">
       <span v-if="completed" class="task--completed">{{title}}</span>
       <span v-else>{{title}}</span>
    </div> -->

    <div :class="{'task task--completed': completed, 'task': !completed}">
        {{title}}
    </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        id: Number,
        title: String,
        completed: Boolean
    }
}
</script>

<style>
.task {
    color: red;
}

.task--completed {
    color: blue;
    text-decoration: line-through;
}
</style>
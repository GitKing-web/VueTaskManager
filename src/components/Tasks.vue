<template>
    <div  :key="task.id" v-for="task in tasks">
        <Task_com @delete-task="$emit('delete-task', task.id)" :task="task" />
    </div>
</template>

<script>

import Task_com from './Task'

export default {
    name: 'Tasks_com',
    props: {
        tasks: Array
    },
    components: {
        Task_com
    },
    emits: ['delete-task']
}
</script>
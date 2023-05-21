<template>
    <div class="task">
        <h4>
            {{ task.text }}
            <button @click="onDelete(task.id)" class="btn">delete</button>
        </h4>
        <p>{{ task.day }}</p>

    </div>
</template>

<script>


    export default{
        name: 'Task_com',
        props: {
            task: Object
        },
        methods: {
            onDelete(id){
                this.$emit('delete-task', id)
            }
        },

    } 
</script>

<style scoped>
.task{
  background-color: #f4f4f4;
  padding: 20px;
  margin-top: 8px;
  color: #000;
}
.task.reminder{
    border-right: 9px solid green;
}
.task h4{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>
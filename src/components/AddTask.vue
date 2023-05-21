<template>
    <form @submit="onSubmit">
        <div class="add-task">
      <legend>Task</legend>
      <input v-model="text" type="text" placeholder="Add Task">
      <legend>Day & Time</legend>
      <input v-model="day" class="" type="text" placeholder="Add Day & Time">
  
      <input style="background: #000; color: #fff; border: none;" type="submit" value="Save Task">
    </div>

    </form>
</template>

<script>
    export default{
        name: 'AddTask_com',
        data() {
            return {
                text: '',
                day: ''
            }
        },
        methods: {
            onSubmit(e) {
                e.preventDefault()
                if(!this.text){
                   return alert('Please add a task')
                }

                const newTask = {
                    id: Math.floor(Math.random() * 9885800),
                    text: this.text,
                    day: this.day
                }
                this.$emit('add-task', newTask)
                this.text = '',
                this.day = ''
            }
        }
    }

</script>
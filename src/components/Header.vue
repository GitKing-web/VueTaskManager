
<template>
    <header>
        <h3>{{ title }}</h3>
        <Button_com @toggle-add-task="$emit('toggle-add-task')" :text="toggleText ? 'Close' : 'AddTask'" :color="toggleText ? 'black' : 'green'" />
    </header>
</template>

<script>

import Button_com from './Button'

export default {
    name: 'Header_com',
    props: {
        title: String,
        toggleText: Boolean
    },
    components: {
        Button_com
    }
}
</script>


<style scoped>
    header{
        display: flex;
        justify-content: space-between;
    }
</style>
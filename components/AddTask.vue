<template>
    <div @click="$emit('add-task')">
        <div class='addTask'>
            Add Task
        </div>
    </div>
</template>

<script>
export default {
    name: 'AddTask',


    emits:[
        'add-task', 
    ],

    // data:() => {
    //     return{

    //     }
    // }
}
</script>

<style scoped>
.addTask{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-self: center;
    text-align: center;
    width: 100px;
    height: 45px;
    border: 1px solid;
    border-radius: 3px;
    cursor: pointer;
}

</style>
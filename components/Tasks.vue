<template>
    <div class='flex'>
        <div class='flex-subcontainer'>
            <div :key="task.id" v-for="task in tasks" class='flex-item' :class="[task.reminder ? 'reminder' : 'none']">
                <Task :task="task" @delete-task="$emit('delete-task', task.id)"/>
            </div>
        </div>
    </div>
</template>

<script>
import Task from "~/components/Task"

export default {
    components: {
        Task,
    },

    name: 'Tasks',
    props: {
        tasks: Array,
    },
    emits:[
        'delete-task'
    ],

}
</script>

<style lang="scss">
@import '~/assets/css/config';

.flex{
    color: $black;
    display:flex;
    flex-direction: row; // Sets the axis of what the child element is editing when using flex
    flex-wrap: nowrap;
    flex:1 1 0px;
    margin: 12px;

    &-subcontainer{
        display:flex;
        flex-direction:column;
        flex:1 0 auto; // Editing row axis, not column axis
        padding: 0 15px;
        align-items: center;
    }

    &-item{
        display: flex;
        flex-direction: row;
        flex:1 0 70px; // Editing column axis due to parent element being set to column axis
        width: 340px; // Editing the current elements width
        margin-top: 15px;
        padding: 10px;
        background: $white;
    }
}        

.reminder{
    border-right: 3px solid #00cc00;
}
</style>
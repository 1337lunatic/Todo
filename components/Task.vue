<template>
    <div class="task">
        <div class="task-elements">
            <h3>{{ task.name }}</h3>
            <p>{{ task.day }}</p>
        </div>
        <button @click="$emit('delete-task', task.id)">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-x" viewBox="0 0 16 16">
                <path d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708z"/>
            </svg>
        </button>
    </div>
</template>

<script>

export default {
    name: 'Task',
    props: {
        task: Object,
    },
}
</script>

<style lang="scss">
@import '~/assets/css/config';
.task{
    display: flex;
    flex: 1 1 0px;

    &-elements{
        display: flex;
        flex-direction: column;
        flex: 1 0 auto;
        align-items: flex-start;
        justify-content: space-evenly;
    }

    button{
        font-size: 24px;
        height: 24px;
        padding: 0;
        border: none;
        cursor: pointer;
        outline: none;
        background: none;
        
        &:hover{
            color: red;
        }
    }
    h3{
        color: $primary-text;
    }
    p{
        color: $secondary-text;
        padding: 0;
        margin: 0;
    }
}

</style>
<template>
    <div class='item-container'>
        <ul :key="item.id" v-for="item in todoitems">
            <li> 
                <div class="card">
                    <p>{{ item.name }}</p>
                    
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
props: ['todoitems']

}
</script>

<style lang="scss">
@import '~/assets/css/config';

.item-container{
    color: $dark-color;
    
    ul {
        margin: 5px;

        li {
            list-style-type: none;
        }
    }
    p{
        padding: 0;
        margin: 0;
    }

}


</style>
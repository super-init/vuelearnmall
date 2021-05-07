<template>
    <div class="goods">
       <goods-list-item v-for="(item,id) in goods" :item="item" :key="id"/>
    </div>
</template>

<script>
    import GoodsListItem from "./goodsListItem";
    export default {
        name: "goodsList",
        components: {GoodsListItem},
        props:{
            goods:{
                type:Array,
                default(){
                    return []
                }
            }
        }
    }
</script>

<style scoped>
    .goods{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        align-items: center;
    }
</style>
<template>
    <div class="goodsItem">
        <img :src="item.show.img">
        <div class="goodsInfo">
            <p>{{item.title}}</p>
            <span class="price">{{item.price}}</span>
            <span class="cfav">{{item.cfav}}</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "goodsListItem",
        props:{
            item:{
                type:Object,
                default(){
                    return {}
                }
            }
        }
    }
</script>

<style scoped>
    .goodsItem{
        position: relative;
        padding-bottom: 30px;
        width: 47%;
        padding-right: 5px;
        /*padding-left: 2px;*/
    }
    img{
        width: 100%;
    }
    .goodsInfo{
        width: 100%;
        font-size: 12px;
        position: absolute;
        bottom: 0;
        overflow: hidden;
        text-align: center;
        padding-bottom: 3px;
    }
    .goodsInfo p{
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
    .price{
        padding-right: 18px;
        color: red;
    }
    .cfav{
        position: relative;
    }
    .cfav::before{
        content: '';
        position: absolute;
        left: -15px;
        top: -1px;
        width: 14px;
        height: 14px;
        background: url("../../../assets/img/home/collect.svg") 0 0/14px 14px;
    }
</style>
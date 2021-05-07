<template>
    <div class="tabControl">
        <div v-for="(item,index) in titles" class="tabControlItem" @click="btnClick(index)">
            <span :class="{active: index==currentIndex}">
            {{item}}
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "tabControl",
        props:{
            titles:{
                type:Array,
                default(){
                    return []
                }
            }
        },
        data(){
            return {
                currentIndex:0
            }
        },
        methods:{
            btnClick(index){
                this.currentIndex=index
            }
        }
    }
</script>

<style scoped>
    .tabControl{
        display: flex;
        background-color: #ffffff;
        height: 32px;
        line-height: 32px;
        z-index: 9;
    }
    .tabControlItem{
        flex: 1;
        text-align: center;
        font-size: 15px;
    }
    span:hover{
        /*width: 32px;*/

    }
    .active{
        border-bottom: 3px solid  var(--color-tint);
        color:  var(--color-tint);
    }
</style>
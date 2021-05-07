<template>
    <div class="nav-bar">
        <div class="left"><slot name="left"></slot></div>
        <div class="center"><slot name="center"></slot></div>
        <div class="right"><slot name="right"></slot></div>
    </div>
</template>

<script>
    export default {
        name: "navbar"
    }
</script>

<style scoped>
    .nav-bar{
        width: 100%;
        display: flex;
        height: 44px;
        line-height: 44px;
        box-shadow: 0 1px 1px rgba(100,100,100,.1);
        position: fixed;
        top: 0;
        left: 0;
        top: 0px;
        z-index: 9;
    }
    .right,.left{
        width: 60px;
        /*background-color: #2c3e50;*/
    }
    .center{
        flex: 1;
        text-align: center;
    }
</style>
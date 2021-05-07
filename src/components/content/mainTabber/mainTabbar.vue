<template>
    <div>
        <TabBar>
            <TabItem path="/home" active-color="blue">
                <template #item-icon><img src="../../../assets/img/tabbar/home.png" alt="首页"></template>
                <template #item-icon-active><img src="../../../assets/img/tabbar/home_active.png"></template>
                <template #item-text>
                    <div>首页</div>
                </template>
            </TabItem>
            <TabItem path="/cart" active-color="red">
                <template #item-icon><img src="../../../assets/img/tabbar/shopcart.png" alt="购物车"></template>
                <template #item-icon-active><img src="../../../assets/img/tabbar/shopcart_active.png"></template>
                <template #item-text>
                    <div>购物车</div>
                </template>
            </TabItem>
            <TabItem path="/category" active-color="orange">
                <template #item-icon><img src="../../../assets/img/tabbar/categories.png" alt="分类"></template>
                <template #item-icon-active><img src="../../../assets/img/tabbar/categories_active.png"></template>
                <template #item-text>
                    <div>分类</div>
                </template>
            </TabItem>
            <TabItem path="/profile" active-color="pink">
                <template #item-icon><img src="../../../assets/img/tabbar/profile.png" alt="我的"></template>
                <template #item-icon-active><img src="../../../assets/img/tabbar/profile_active.png"></template>
                <template #item-text>
                    <div>我的</div>
                </template>
            </TabItem>
        </TabBar>
    </div>
</template>

<script>
    import TabBar from "../../common/TabBar"
    import TabItem from "../../common/TabItem";

    export default {
        name: "mainTabbar",
        components: {
            TabBar,
            TabItem
        }
    }
</script>

<style scoped>

</style>
<template>
    <Swiper>
        <SwiperItem v-for="(item,index) in banner" :key="index">
            <a :href="item.link">
                <img :src="item.image"/>
            </a>
        </SwiperItem>
    </Swiper>
</template>

<script>
    import {Swiper,SwiperItem} from "../../../components/common/swiper"
    export default {
        name: "HomeSwiper",
        props:{
            banner:{
                type:Array,
                default(){
                    return []
                }
            }
        },
        components:{
            SwiperItem,
            Swiper
        }
    }
</script>

<style scoped>

</style>
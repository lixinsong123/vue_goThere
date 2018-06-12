<template>
    <div>
        <home-header></home-header>
        <hoem-swiper></hoem-swiper>
    </div>
</template>

<script>
import HomeHeader from "./components/Header";
import HoemSwiper from "./components/Swiper";
export default {
    name: 'home',
    data(){
        return{
        }
    },
    components: {
        HomeHeader,
        HoemSwiper
    }
}
</script>

<style>

</style>

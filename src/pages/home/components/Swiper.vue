<template>
    <div class="wrapper">
        <swiper :options="swiperOption" ref="mySwiper">
            <!-- slides -->
            <swiper-slide v-for="(item) in swiperList "
                :key = 'item.id'
            >
                <img class="swiper-img" :src="item.imgUrl" alt="">
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    data() {
      return {
        swiperOption: {
          // some swiper options/callbacks
          // 所有的参数同 swiper 官方 api 参数
          // ...
            pagination: '.swiper-pagination',
            loop: true
        },
        swiperList: [
            {
                id: '1',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/fc/e47aa3e1c67bbc02.jpg_750x200_0f3eecf8.jpg'
            },
            {
                id: '2',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/bd/a46742f7247f4f02.jpg_750x200_494b1819.jpg'
            },
            {
                id: '3',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/ec/865b3fa81806f802.jpg_750x200_7ae07dcd.jpg'
            },
            {
                id: '4',
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/13/6332699c44387902.jpg_750x200_b7afa4f8.jpg'
            }
        ]
      }
    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.swiper
      }
    },
    mounted() {
      // current swiper instance
      // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
      console.log('this is current swiper instance object', this.swiper)
      //this.swiper.slideTo(3, 1000, false)
    }
}
</script>

<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active
        background: #ffffff
    .wrapper >>> .swiper-pagination-bullet
        width: 6px
        height: 6px
    .wrapper
        width: 100%
        height: 0
        overflow: hidden
        padding-bottom: 26.5%
        .swiper-img
            width: 100%
</style>

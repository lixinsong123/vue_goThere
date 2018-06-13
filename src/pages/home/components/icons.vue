<template>
    <div class="icons">
         <swiper  ref="mySwiper">
                <!-- slides -->
                <swiper-slide  
                       v-for="(page,index) in pages " :key ="index"
                >
                         <div class="icon" v-for="(item,sindex) in page " :key ="sindex" >
                            <div class="icon-img">
                                <img class="icon-imgContent" :src="item.imgUrl" alt="">
                            </div> 
                            <p class="icon-desc">{{item.text}}</p>
                        </div>
                </swiper-slide>
                <!-- Optional controls -->
                <div class="swiper-pagination"  slot="pagination"></div>     
        </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeIcos',
    data(){
        return {
            iconsLiist: [
                {
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                    text: '景点门票'
                },
                {
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png',
                    text: 'Q+精选'
                },
                {
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
                    text: '必游榜单'
                },
                {
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
                    text: '踏青赏花'
                },
                {
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
                    text: '一日游'
                },
                {
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png',
                    text: '游船游艇'
                },
                {
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
                    text: '神秘武隆'
                },
                {
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
                    text: '演出'
                },
                {
                    imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
                    text: '演出'
                }
            ]
        }
    },
    computed: {
        pages(){
            const pages = [];
            this.iconsLiist.forEach((item,index)=>{
                const page = Math.floor(index/8);
                if(!pages[page]){
                    pages[page] = [];
                }
                pages[page].push(item);
            });
            return pages;
        }
    }
}
</script>

<style lang="stylus" scoped>
    @import  "~styles/varibles.styl";
    @import  "~styles/mixins.styl";
    .icons >>> swiper-container
        padding-bottom: 50%
        overflow: hidden
    .icon
        position: relative
        overflow: hidden
        width: 25%
        float: left 
        height: 0
        padding-bottom: 25%
        .icon-img
            position: absolute
            top: 0 
            left: 0
            right: 0
            bottom: .44rem
            box-sizing border-box;
            padding: .1rem
            .icon-imgContent
                display:block
                margin: 0 auto
                height: 100%
                padding-top: .14rem
        .icon-desc
            position: absolute
            left: 0
            right: 0
            bottom: 0
            height: .44rem
            line-height: .44rem
            text-align: center
            color: $darkTextColor
            ellipsis()
</style>

<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div 
                class="icon"
                v-for="item of page"
                :key="item.id">
                    <div class="icon-img">
                        <img class="icon-img-content" src="item.imgUrl">
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeIcons',
    data () {
        return {
            iconList: [{
                id: '0001',
                imgUrl: '//s.qunarzz.com/homenode/images/touchheader/hotel.png',
                desc: '酒店'
            },{
                id: '0002',
                imgUrl: '//s.qunarzz.com/homenode/images/touchheader/train.png',
                desc: '火车票'
            },{
                id: '0003',
                imgUrl: '//s.qunarzz.com/homenode/images/touchheader/flight.png',
                desc: '机票'
            },{
                id: '0004',
                imgUrl: '//s.qunarzz.com/homenode/images/touchheader/package.png',
                desc: '度假'
            },{
                id: '0005',
                imgUrl: 'https://picbed.qunarzz.com/377db8cb2143aebf01869c9baad3d325.png',
                desc: '汽车·船票'
            },{
                id: '0006',
                imgUrl: 'https://picbed.qunarzz.com/f5e5770393d759578962e53ee67798c8.png',
                desc: '海外酒店'
            },{
                id: '0007',
                imgUrl: '//s.qunarzz.com/homenode/images/touchheader/train.png',
                desc: '火车票'
            },{
                id: '0008',
                imgUrl: 'https://picbed.qunarzz.com/a36d2288f19e54562338f4d8ef986288.png',
                desc: '低价机票'
                },{
                id: '0009',
                imgUrl: '//s.qunarzz.com/homenode/images/touchheader/piao.png',
                desc: '景点门票'
            }]
        }
    },
    computed: {
        pages () {
            const pages = []
            this.iconList.forEach((item, index) => {
                const page = Math.floor( index / 8)
                if( !pages[page]) {
                    pages[page] = []
                }
                pages[page].push(item)
            })
            return pages
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
@import '~styles/mixins.styl'
    .icons>>> .swiper-container{
        margin-top :.2rem
        overflow : hidden
        height : 0
        padding-bottom : 50%  //宽高比是2：1
    }
    .icon{
        position :relative
        overflow :hidden
        float :left
        width :25%
        height :0
        padding-bottom :25%
    }
    .icon-img{
        position :absolute
        top : 0
        left : 0
        right :0
        bottom :.44rem //给标签留的位置
        box-sizing : border-box
        padding :.1rem
    }
    .icon-img-content{
        height :100%
        display :block
        margin : 0 auto //这个和上一条使图片自动居中
    }
    .icon-desc{
        position : absolute
        left : 0
        right : 0
        bottom : 0
        height : .44rem
        line-height : .44rem
        text-align : center
        color : $darkTextColor
        ellipsis ()
    }
</style>
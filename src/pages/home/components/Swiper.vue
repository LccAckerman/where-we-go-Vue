<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="item of SwiperList" :key="item.id">
            <img class="swiper-image" :src="item.imgUrl">
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    data(){
        return {
            swiperOption:{
                pagination: '.swiper-pagination',
                loop: true
            },
            SwiperList:[{
                id: '0001',
                imgUrl: "//mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/3f5ff03fa0c024b930f515e63ae2c702.jpg_945x288_7dff4510.jpg"
            },{
                id: '0002',
                imgUrl: "//h-des-activity-fecp.qunarzz.com/h_des_activity_fe_h_des_activity_fe/973dc1ae0da73a58410186df08ff25cb.jpg"
            }]
        }
    }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active{
    background-color : #ffffff
}
.wrapper{
    width :100%
    height :0
    overflow : hidden
    padding-bottom :30.47%
    background-color :#eee
}
.swiper-image{
    width :100%
}
</style>
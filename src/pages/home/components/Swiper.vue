<template>
<div class="wrapper">
  <swiper ref="mySwiper" :options="swiperOptions">
    <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="抱歉，图片加载错误">
    </swiper-slide>
    <!-- 用来显示分页的内容 -->
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOptions: {
        loop: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        }
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://img1.qunarzz.com/qs/2101/87/f3fa48c8346dab02.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://img1.qunarzz.com/qs/2101/e8/3823364f76ded302.jpg'
      }, {
        id: '0003',
        imgUrl: 'https://img1.qunarzz.com/qs/2101/26/bd4db8b1e8de6302.jpg'
      }]
    }
  }
}
</script>

<style lang='stylus' scoped>
//    >>>无视scoped的影响，进行样式穿透
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff !important
  .wrapper
      overflow:hidden
      width: 100%;
      height: 50vw
      .swiper-img
          width:100%
</style>

<template>
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide" v-for="value in run" :style="{backgroundImage: 'url(' + value.imgs + ')'}"></div>
    </div>
    <div class="swiper-pagination swiper-pagination-white"></div>
  </div>
</template>

<script>
  import Swiper from 'swiper';
  import '../assets/css/swiper-3.4.2.min.css';
  export default {
    data(){
      return{
        run: [
          {
            'imgs': '../../static/img/tb_run1.jpg'
          }, {
            'imgs': '../../static/img/tb_run2.jpg'
          }, {
            'imgs': '../../static/img/tb_run3.jpg'
          }, {
            'imgs': '../../static/img/tb_run4.jpg'
          }
        ],
      }
    },
    mounted() {
      console.log('mounted', this)
      var swiper = new Swiper('.swiper-container', {
        pagination: '.swiper-pagination',
        paginationClickable: false,
        loop: true,
        speed: 600,
        autoplay: 1000,
        onTouchEnd() {
          swiper.startAutoplay()
          console.log("asd")
        },
      });
    },
    methods:{
    }
  }
</script>

<style lang="less">
  .swiper-container {
    width: 100%;
    height: 10rem;
    .swiper-wrapper {
      width: 100%;
      height: 100%;
    }
    .swiper-slide {
      background-position: center;
      background-size: cover;
      width: 100%;
      height: 100%;
      img {
        width: 100%;
        height: 100%;
      }
    }
    .swiper-pagination-bullet {
      width:0.833rem;
      height: 0.833rem;
      display: inline-block;
      background: #3385FF;
    }
  }
</style>

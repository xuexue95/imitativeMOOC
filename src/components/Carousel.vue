<template>
  <div class="carousel" @mouseover="stop" @mouseout="begin">
    <transition-group tag="ul" name="fade">
      <li v-for="(item,index) in carouselList" :key="index" v-show="index == currentIndex">
        <img :src="item.src" alt class="carousel-img" />
      </li>
    </transition-group>
    <div class="jiantou last" @click="lastImg">
      <i class="iconfont icon-houtui"></i>
    </div>
    <div class="jiantou next" @click="nextImg">
      <i class="iconfont icon-qianjin"></i>
    </div>
    <div class="banner-dots">
      <span
        class="dot"
        v-for="(item,index) in carouselList"
        :key="index"
        :class="{active: index == currentIndex ? true:false} " @click="changeImg(index)"
      ></span>
    </div>
  </div>
</template>

<script>
export default {
  name: "carousel",
  porps: {},
  data() {
    return {
      carouselList: [
        { src: require("../assets/lunbo1.jpg") },
        { src: require("../assets/lunbo2.jpg") },
        { src: require("../assets/lunbo3.jpg") },
        { src: require("../assets/lunbo4.jpg") },
        { src: require("../assets/lunbo5.jpg") },
        { src: require("../assets/lunbo6.jpg") }
      ],
      currentIndex: 0,
      carouselTimer: null
    };
  },
  mounted() {
    this.begin();
  },
  methods: {
    autoPlay() {
      this.currentIndex++;
      if (this.currentIndex >= this.carouselList.length) {
        this.currentIndex = 0;
      }
    },

    begin() {
      this.stop();
      this.carouselTimer = setInterval(this.autoPlay, 2000);
    },
    
    stop() {
      clearInterval(this.carouselTimer);
    },

    lastImg() {
      this.currentIndex--;
      if (this.currentIndex < 0) {
        this.currentIndex = this.carouselList.length - 1;
      }
      console.log(this.currentIndex);
    },

    nextImg() {
      this.currentIndex++;
      if (this.currentIndex >= this.carouselList.length) {
        this.currentIndex = 0;
      }
      console.log(this.currentIndex);
    },

    changeImg(index){
        this.currentIndex = index;
    },
  }
};
</script>

<style scoped lang='scss'>
.jiantou {
  width: 50px;
  height: 50px;
  background: rgb(0, 0, 0, 0.1);
  border-radius: 50%;
  text-align: center;
  line-height: 50px;
  color: #fff;
}
.jiantou:hover {
  background: rgb(0, 0, 0, 0.4);
}

.carousel {
  width: 100%;
  height: 100%;
  position: relative;

  li {
    width: 100%;
    height: 100%;
    position: absolute;
    left: 0;
    top: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    img {
      width: 100%;
    }
  }

  .last {
    position: absolute;
    left: 15px;
    top: 50%;
    margin-top: -25px;
  }
  .next {
    position: absolute;
    right: 15px;
    top: 50%;
    margin-top: -25px;
  }
}

.banner-dots {
  position: absolute;
  bottom: 20px;
  left: 0;
  right: 0;
  text-align: right;
  padding-right: 24px;
  line-height: 12px;

  .dot {
    display: inline-block;
    width: 8px;
    height: 8px;
    border-radius: 4px;
    margin-right: 8px;
    background: rgba(255, 255, 255, 0.7);
  }
  .dot.active {
    width: 20px;
  }
}
// 动画
.fade-enter-active,
.fade-leave-active {
  transition: all 1s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
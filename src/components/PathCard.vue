<template>
  <div class="course-path-container">
    <a href>
      <div class="course-banner">
        <div
          class="img-up"
          :style="{backgroundImage:backgroundImage}"
        ></div>
        <div
          class="img-mid"
          :style="{backgroundImage:backgroundImage}"
        ></div>
        <div
          class="img-down"
          :style="{backgroundImage:backgroundImage}"
        ></div>
      </div>
      <h4>{{pathCardItem.title}}</h4>
      <p>路线吃透面试学问，伴随身为Java工程师的你一路成长，高效充分准备面试拿offer。</p>
      <div class="course-path-info">
        <span>5步骤 · 6门课</span>
        <span>
          <i class="iconfont icon-shoucang"></i>9643人收藏
        </span>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  name: "pathCard",
  props: {
    pathCardItem: {}
  },
  data() {
    return {
        backgroundImage:'url('+ this.pathCardItem.imgUrl+')',
    };
  }
};
</script>
<style scoped lang="scss">
.course-path-container {
  float: left;
  margin-left: 24px;
  margin-bottom: 24px;
  width: 564px;
  height: 148px;

  h4 {
    margin: 8px 0;
    margin-left: 164px;
    font-size: 16px;
    color: #1c1f21;
    line-height: 20px;
    font-weight: bold;
    overflow: hidden;
  }
  p {
    margin-left: 164px;
    font-size: 14px;
    color: #545c63;
    letter-spacing: 0;
    line-height: 20px;
    height: 60px;
    overflow: hidden;
  }
  a {
    .course-banner {
      float: left;
      position: relative;
      transition: all 0.3s;
      width: 140px;
      height: 140px;
      background-color: #f3f5f7;
      border-radius: 8px;

      .img-up,
      .img-mid,
      .img-down {
        margin: 0 auto;
        position: absolute;
        border-radius: 8px;
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        transition: all 0.3s;
      }
      .img-up {
        left: 0px;
        top: 0;
        width: 140px;
        height: 140px;
        z-index: 3;
      }
      .img-mid {
        top: 4px;
        left: 4px;
        width: 132px;
        height: 140px;
        opacity: 0.4;
        z-index: 2;
      }
      .img-down {
        top: 8px;
        left: 8px;
        width: 124px;
        height: 140px;
        opacity: 0.2;
        z-index: 1;
      }
    }
  }
  .course-path-info {
    margin-left: 164px;
    font-size: 12px;
    color: #9199a1;
    height: 18px;
    line-height: 18px;

    .iconfont {
      margin-left: 33px;
    }
  }
}
.course-path-container:hover {
  a {
    .img-up {
      top: -4px;
    }
    .img-mid {
      top: 2px;
    }
    .img-down {
      top: 7px;
    }
    h4 {
      color: #f20d0d;
    }
  }
}
</style>
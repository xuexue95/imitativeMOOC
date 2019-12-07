<template>
  <div class="course-read-container">
    <div class="course-banner">
      <a href>
        <img :src="readCardItem.imgUrl" alt />
        <div class="try-read-img"></div>
      </a>
    </div>

    <h4>
      <a href>{{readCardItem.title}}</a>
    </h4>

    <div class="course-read-info">
      <span>共39节 · 806人已购买</span>
    </div>

    <div class="course-read-teacher">
      <a href>
        <span>Lison</span>
        / 前端高级工程师
      </a>
    </div>

    <div class="course-read-price">
        <span class="sale">¥ {{readCardItem.price}}</span>
    </div>
  </div>
</template>

<script >
export default {
  name: "readCard",
  props: {readCardItem:{}},
  data() {
    return {};
  }
};
</script>

<style lang="scss" scoped>
.course-read-container {
  float: left;
  padding: 18px;
  margin-left: 24px;
  margin-bottom: 24px;
  width: 332px;
  height: 174px;
  transition: all 0.3s;
  .course-banner {
    float: left;
    position: relative;

    img {
      height: 118px;
      width: 104px;
    }
    .try-read-img {
      margin-top: 5px;
      background: url("https://www.imooc.com/static/img/column/try-read-img_new_2x.png");
      background-repeat: no-repeat;
      background-size: 34px auto;
      background-position: center;
      width: 30px;
      height: 20px;
    }
  }

  h4 {
    margin-left: 112px;
    font-size: 14px;
    line-height: 22px;
    height: 44px;
    font-weight: bold;
    overflow: hidden;
    a {
      color: black;
    }
    a:hover {
      color: #3377ff;
    }
  }

  .course-read-info {
    margin-left: 112px;
    padding: 10px 0;
    font-size: 12px;
    color: #9199a1;
    line-height: 14px;
    border-bottom: 1px solid rgba(28, 31, 33, 0.1);
  }
  .course-read-teacher {
    margin: 10px 0;
    margin-left: 112px;
    font-size: 12px;
    color: #1c1f21;
    text-align: left;
    line-height: 16px;
    overflow: hidden;
    height: 16px;

    a {
      color: #1c1f21;

      span {
        font-weight: bold;
      }
    }
  }

  .course-read-price {
    margin-left: 112px;
    margin-top: 17px;
    position: relative;

    .sale {
      font-size: 16px;
      color: #3377ff;
      text-align: left;
      line-height: 32px;
      font-weight: bold;
    }
  }
}
.course-read-container:hover{
    background: #FFFFFF;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1);
    border-radius: 8px;
}
</style>
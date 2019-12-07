<template>
<div class="course-card-container">
    <a href class="course-card">
      <div
        class="course-stat"
        :class="{new:courseCardItem.courseSata.isNew, upgrade:courseCardItem.courseSata.isUpgrade}"
        v-if="courseCardItem.courseSata.sata"
      >{{courseCardItem.courseSata.sata}}</div>
      <div class="course-card-top">
        <img :src="courseCardItem.Imgsrc" alt class="course-banner" />
        <div class="course-label">
          <label v-for="(item,index) in courseCardItem.label" :key="index">{{item}}</label>
        </div>
      </div>
      <div class="course-card-content">
        <h3 class="course-card-name">{{courseCardItem.courseCardName}}</h3>
        <div class="course-card-bottom">
          <div class="course-card-info">
            <span>{{courseCardItem.grade}}</span>
            <span>
              <i class="iconfont icon-tubiaozhizuomoban"></i>
              {{courseCardItem.numberOfPeople}}
            </span>
            <span>评分: {{courseCardItem.score}}</span>
          </div>
          <div
            class="course-card-price"
            :class="{sales:courseCardItem.isSales}"
          >￥{{courseCardItem.price}}</div>
        </div>
      </div>
    </a>
    </div>
</template>

<script>
export default {
  name: "courseCard",
  props: {
      courseCardItem:'',
  },
};
</script>

<style scoped lang="scss">

.new {
  background-color: #ffaa00;
  background-image: linear-gradient(90deg, #ffaa00 17%, #f76b1c 100%);
}

.upgrade {
  background-color: #9447eb;
  background-image: linear-gradient(90deg, #bd89f8 6%, #9447eb 93%);
}

.course-card-container {
    float: left;
    margin-left: 24px;
    border-radius: 4px;
    margin-bottom: 12px;
    width: 270px;
    height: 268px;
    position: relative;
    transition: 0.3s all linear;

    .course-card {
      .course-stat {
        position: absolute;
        border: 2px solid #ffffff;
        border-radius: 12px;
        top: 8px;
        left: -8px;
        z-index: 4;
        font-size: 12px;
        color: #ffffff;
        line-height: 20px;
        padding: 0 8px;
      }
      .course-card-top {
        width: 270px;
        height: 148px;
        position: relative;
        border-radius: 8px;
        transition: all 0.3s;

        .course-banner {
          width: 100%;
          width: 100%;
          height: 100%;
          border-radius: 8px;
        }
        .course-label {
          position: absolute;
          bottom: 6px;
          left: 8px;
          font-size: 12px;
          color: #ffffff;
          line-height: 16px;

          label {
            display: inline-block;
            background: rgba(28, 31, 33, 0.6);
            border-radius: 4px;
            padding: 4px 8px;
            margin-right: 4px;
            margin-bottom: 2px;
            font-weight: 200;
          }
        }
      }

      .course-card-content {
        padding: 8px;

        .course-card-name {
          font-size: 16px;
          color: #07111b;
          line-height: 24px;
          height: 46px;
          transition: all 0.2s;
        }

        .course-card-bottom {
          .course-card-info {
            font-size: 12px;
            color: #93999f;
            line-height: 24px;
            margin-top: 8px;

            span {
              margin-right: 12px;
            }
          }

          .course-card-price {
            font-size: 12px;
            color: #545c63;
          }
          .sales {
            color: #f01414 !important;
            font-weight: bold;
          }
        }
      }
    }

    .course-card:hover {
      .course-card-top {
        box-shadow: 0 3px 8px 0 rgba(0, 0, 0, 0.239);
      }
      .course-card-name {
        color: #f81804;
      }
    }
  }
</style>
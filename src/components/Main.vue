<template>
  <div class="main">
    <!-- 第一块 -->
    <div class="bjfff banner-box">
      <div class="banner" @mouseleave="changeItemOnIndex(-1)">
        <div class="menuwrap"></div>
        <div
          class="submenu"
          v-for="(menuContent,index) in menuContentData"
          :key="index"
          v-show="index == itemOnIndex"
        >
          <div class="innerBox">
            <div class="cates-box" v-for="(title,index) in menuContent.base.title" :key="index">
              <div class="banner-line">
                <span>{{title}}</span>
              </div>
              <div class="tag-box">
                <a href v-for="(tag,index) in menuContent.base.tag" :key="index">{{tag}}</a>
              </div>
            </div>
          </div>
          <div class="recomment-box">
            <!--  -->
            <div class="banner-course-card l">
              <a href>
                <img
                  src="//img3.mukewang.com/szimg/5afb8aa900014cc705400300-360-202.jpg"
                  alt
                  class="l"
                />
                <div class="course-card">
                  <h3 class="course-card-name">Spring Boot仿抖音短视频小程序开发 全栈式实战项目</h3>
                  <div class="course-card-price l">￥348.00</div>
                  <div class="course-card-dot l">
                    <i class="iconfont icon-dian"></i>
                  </div>
                  <div class="course-card-info l">中级</div>
                  <div class="course-card-dot l">
                    <i class="iconfont icon-dian"></i>
                  </div>
                  <div class="course-card-info l">
                    <i class="iconfont icon-tubiaozhizuomoban" style="font-size:12px;"></i>
                    1672
                  </div>
                </div>
              </a>
            </div>
            <!--  -->
            <div class="banner-course-card l">
              <a href>
                <img
                  src="//img3.mukewang.com/szimg/5afb8aa900014cc705400300-360-202.jpg"
                  alt
                  class="l"
                />
                <div class="course-card">
                  <h3 class="course-card-name">Spring Boot仿抖音短视频小程序开发 全栈式实战项目</h3>
                  <div class="course-card-price l">￥348.00</div>
                  <div class="course-card-dot l">
                    <i class="iconfont icon-dian"></i>
                  </div>
                  <div class="course-card-info l">中级</div>
                  <div class="course-card-dot l">
                    <i class="iconfont icon-dian"></i>
                  </div>
                  <div class="course-card-info l">
                    <i class="iconfont icon-tubiaozhizuomoban" style="font-size:12px;"></i>
                    1672
                  </div>
                </div>
              </a>
            </div>
            <div class="banner-course-card l">
              <a href>
                <img
                  src="//img3.mukewang.com/szimg/5afb8aa900014cc705400300-360-202.jpg"
                  alt
                  class="l"
                />
                <div class="course-card">
                  <h3 class="course-card-name">Spring Boot仿抖音短视频小程序开发 全栈式实战项目</h3>
                  <div class="course-card-price l">￥348.00</div>
                  <div class="course-card-dot l">
                    <i class="iconfont icon-dian"></i>
                  </div>
                  <div class="course-card-info l">中级</div>
                  <div class="course-card-dot l">
                    <i class="iconfont icon-dian"></i>
                  </div>
                  <div class="course-card-info l">
                    <i class="iconfont icon-tubiaozhizuomoban" style="font-size:12px;"></i>
                    1672
                  </div>
                </div>
              </a>
            </div>
            <!--  -->
          </div>
        </div>
        <div class="menuContent">
          <div
            class="item"
            v-for="(item,index) in menuContentData"
            :key="index"
            :class="{itemOn:index == itemOnIndex }"
            @mouseenter="changeItemOnIndex(index)"
          >
            <a href>
              <span class="group">{{item.group}}</span>
              <i class="iconfont icon-triangle-down"></i>
            </a>
          </div>
        </div>

        <div class="banner-content">
          <Carousel />
        </div>
      </div>
      <div class="container-types container-recommend">
        <h3 class="types-title">
          <span>就业班</span>
          <span class="intro">零基础快速就业</span>
        </h3>
        <div class="clear"></div>

        <div class="path-list">
          <a href v-for="(item,index) in pathListData" :key="index">
            <i :class="item.class"></i>
            <p class="title">{{item.title}}</p>
            <p class="desc">{{item.desc}}</p>
          </a>
          <div class="clear"></div>
        </div>
      </div>

      <div class="container-types container-recommend">
        <h3 class="types-title">
          <span>职场进阶</span>
          <span class="intro">1年以上开发经验系统成长</span>
        </h3>
        <div class="clear"></div>
        <div class="path-list"></div>
      </div>
    </div>

    <!-- 第二块 -->
    <div class="bj000">
      <div class="container-types">
        <h3 class="types-title">
          <span>课程推荐</span>
        </h3>
        <div class="clear"></div>
        <div class="types-content">
          <CourseCard
            :courseCardItem="courseCardItem"
            v-for="(courseCardItem,index) in courseCardData"
            :key="index"
          />
          <div class="clear"></div>
        </div>
      </div>
    </div>

    <!-- 第三块 -->
    <div class="bjfff">
      <div class="container-types">
        <h3 class="types-title">
          <span>学习路线</span>
          <ul class="js-path-tab">
            <li
              v-for="(item,index) in pathTab"
              :key="index"
              :class="{curr:index == pathTabIndex }"
              @click="changePathTabIndex(index)"
            >{{item}}</li>
          </ul>
          <a href class="more">
            查看更多
            <i class="iconfont icon-qianjin"></i>
          </a>
          <div class="clear"></div>
        </h3>
        <div class="types-content">
          <PathCard
            v-for="(pathCardItem,index) in pathCardData"
            :pathCardItem="pathCardItem"
            :key="index"
          />

          <div class="clear"></div>
        </div>
      </div>
    </div>

    <!-- 第四块 -->
    <div class="bj000">
      <div class="container-types container-read">
        <h3 class="types-title">
          <span>慕课专栏</span>
          <a href class="more">
            查看更多
            <i class="iconfont icon-qianjin"></i>
          </a>
        </h3>
        <div class="clear"></div>
        <div class="types-content">
          <ReadCard
            v-for="(readCardItem,index) in readCardData"
            :readCardItem="readCardItem"
            :key="index"
          />
          <div class="clear"></div>
        </div>
      </div>
    </div>

    <!-- 第五块 -->
    <div class="bjfff">
      <div class="container-types">
        <h3 class="types-title">
          <span>排行榜</span>
          <ul class="js-rank-tab">
            <li
              v-for="(item,index) in rankTab"
              :class="{curr:index == rankTabIndex }"
              @click="changeRankTabIndex(index)
            "
              :key="index"
            >{{item}}</li>
          </ul>
          <div class="rank-info r">
            <i class="iconfont icon-wenhao"></i>
            <dl class="info">
              <dt>实战课排行榜规则</dt>
              <dd>根据近30天购买人数由高到低进行推荐</dd>
              <dt class="free">免费课排行榜规则</dt>
              <dd>根据近30天观看人数由高到低进行推荐</dd>
            </dl>
          </div>
        </h3>

        <div class="clear"></div>
        <div class="types-content">
          <CourseCard
            :courseCardItem="courseCardItem"
            v-for="(courseCardItem,index) in courseCardData"
            :key="index"
          />
          <div class="clear"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script >
import Carousel from "@/components/Carousel.vue";
import CourseCard from "@/components/CourseCard.vue";
import PathCard from "@/components/PathCard.vue";
import ReadCard from "@/components/ReadCard.vue";
export default {
  name: "main-page",
  components: {
    Carousel,
    CourseCard,
    PathCard,
    ReadCard
  },
  data() {
    return {
      pathListData: [
        {
          title: "Web前端攻城狮",
          desc: "从未接触编程也可以学好",
          class: "i-web"
        },
        { title: "Java攻城狮", desc: "综合就业排名第一", class: "i-java" },
        { title: "Python攻城狮", desc: "应用领域最为广泛", class: "i-python" },
        {
          title: "Android攻城狮",
          desc: "移动市场份额第一",
          class: "i-android"
        },
        { title: "PHP攻城狮", desc: "Web开发首选语言", class: "i-php" }
      ],
      courseCardData: [
        {
          courseSata: {
            sata: "新课",
            isNew: true,
            isUpgrade: false
          },
          Imgsrc:
            "//img3.mukewang.com/szimg/5d78c03b08bac0da06000338-360-202.jpg",
          label: ["Java"],
          courseCardName: "告别996，开启Java高效编程之门",
          grade: "初级",
          numberOfPeople: "305",
          score: "10.00",
          isSales: true,
          price: "249.00"
        },
        {
          courseSata: {
            sata: "新课",
            isNew: true,
            isUpgrade: false
          },
          Imgsrc:
            "//img3.mukewang.com/szimg/5d771ec709f8709812000676-360-202.png",
          label: ["SpringBoot", "Spring Cloud"],
          courseCardName: "Spring Cloud微服务安全实战",
          grade: "中级",
          numberOfPeople: "282",
          score: "10.00",
          isSales: true,
          price: "255.00"
        },
        {
          courseSata: {
            sata: "",
            isNew: true,
            isUpgrade: false
          },
          Imgsrc:
            "//img2.mukewang.com/szimg/5c18d2d8000141c506000338-360-202.jpg",
          label: ["Java", "算法与数据结构"],
          courseCardName: "剑指Java面试-Offer直通车",
          grade: "中级",
          numberOfPeople: "4461",
          score: " 9.97",
          isSales: false,
          price: "299.00"
        },
        {
          courseSata: {
            sata: "",
            isNew: true,
            isUpgrade: false
          },
          Imgsrc:
            "//img2.mukewang.com/szimg/5d4ceaef09c3cb6612000676-360-202.png",
          label: ["Java"],
          courseCardName: "Java并发编程精讲",
          grade: "中级",
          numberOfPeople: "740",
          score: "10.00",
          isSales: false,
          price: "348.00"
        },
        {
          courseSata: {
            sata: "",
            isNew: true,
            isUpgrade: false
          },
          Imgsrc:
            "//img3.mukewang.com/szimg/5d1032ab08719e0906000338-360-202.jpg",
          label: ["Java"],
          courseCardName: "告别996，开启Java高效编程之门",
          grade: "初级",
          numberOfPeople: "305",
          score: "10.00",
          isSales: false,
          price: "249.00"
        },
        {
          courseSata: {
            sata: "",
            isNew: true,
            isUpgrade: false
          },
          Imgsrc:
            "//img2.mukewang.com/szimg/5d5e6d1f0983ee0112000676-360-202.png",
          label: ["SpringBoot", "Spring Cloud"],
          courseCardName: "Spring Cloud微服务安全实战",
          grade: "中级",
          numberOfPeople: "282",
          score: "10.00",
          isSales: false,
          price: "255.00"
        },
        {
          courseSata: {
            sata: "",
            isNew: true,
            isUpgrade: false
          },
          Imgsrc:
            "//img1.mukewang.com/szimg/5ad05dc00001eae705400300-360-202.jpg",
          label: ["Java", "算法与数据结构"],
          courseCardName: "剑指Java面试-Offer直通车",
          grade: "中级",
          numberOfPeople: "4461",
          score: " 9.97",
          isSales: false,
          price: "299.00"
        },
        {
          courseSata: {
            sata: "升级",
            isNew: false,
            isUpgrade: true
          },
          Imgsrc:
            "//img4.mukewang.com/szimg/5c7e6835087ef3d806000338-360-202.jpg",
          label: ["Java"],
          courseCardName: "Java并发编程精讲",
          grade: "中级",
          numberOfPeople: "740",
          score: "10.00",
          isSales: false,
          price: "348.00"
        }
      ],
      pathTab: [
        "热门",
        "前端",
        "后端",
        "移动端",
        "计算机基础",
        "大数据",
        "测试"
      ],
      rankTab: ["实战课程", "免费课程"],
      pathCardData: [
        {
          title: "Java从初级到高级的进阶面试线路图",
          imgUrl:
            "//img3.mukewang.com/szimg/5d8b22e4080de9a601400140-140-140.jpg"
        },
        {
          title: "Vue.js从入门到全栈开发",
          imgUrl:
            "//img4.mukewang.com/szimg/5d8b2230089487a301400140-140-140.jpg"
        },
        {
          title: "从功能测试到自动化测试转型路线",
          imgUrl:
            "//img1.mukewang.com/szimg/5d8b2b76088261f301400140-140-140.jpg"
        },
        {
          title: "计算机基础学习路线",
          imgUrl:
            "//img1.mukewang.com/szimg/5d8b2a0608bd096301400140-140-140.jpg"
        }
      ],
      readCardData: [
        {
          title: "零基础学透 TypeScript",
          imgUrl: "//img.mukewang.com/5d5bd42b000185c402940333.jpg",
          price: "68.00"
        },
        {
          title: "面试官系统精讲Java源码及大厂真题",
          imgUrl: "//img2.mukewang.com/5d64c20c0001937e02940333.jpg",
          price: "68.00"
        },
        {
          title: "Git原理详解与实操指南",
          imgUrl: "//img4.mukewang.com/5d882d04000187db02940333.jpg",
          price: "38.00"
        },
        {
          title: "你不知道的前端性能优化技巧",
          imgUrl: "//img.mukewang.com/5d5bd510000104f102940333.jpg",
          price: "48.00"
        },
        {
          title: "Linux命令行与Shell脚本编程大全",
          imgUrl: "//img.mukewang.com/5d5bd46e0001487102940333.jpg",
          price: "68.00"
        },
        {
          title: "一线数据库工程师带你深入理解 MySQL",
          imgUrl: "//img1.mukewang.com/5d5bd53d00019b5302940333.jpg",
          price: "46.00"
        }
      ],
      menuContentData: [
        {
          group: "前沿 / 区块链 / 人工智能",
          base: {
            title: ["前沿技术"],
            tag: [
              "微服务",
              "区块链",
              "以太坊",
              "机器学习",
              "深度学习",
              "计算机视觉",
              "数据分析&挖掘"
            ]
          }
        },
        {
          group: "前端 / 小程序 / JS",
          base: {
            title: ["前端开发"],
            tag: [
              "HTML/CSS JavaScript",
              "Vue.js",
              "React.JS",
              "Angular",
              "Node.js",
              "jQuery",
              "Bootstrap",
              "Sass/Less",
              "WebApp",
              "小程序",
              "前端工具",
              "Html5",
              "CSS3"
            ]
          }
        },
        {
          group: "后端 / JAVA / Python",
          base: {
            title: ["后端开发"],
            tag: [
              "Java",
              "SpringBoot",
              "Spring",
              "Cloud",
              "Python",
              "爬虫",
              "Django",
              "Tornado",
              "Go",
              "PHP",
              "C",
              "C++",
              "C#",
              "Ruby"
            ]
          }
        },
        {
          group: "移动 / Android / iOS",
          base: {
            title: ["移动开发"],
            tag: ["Android", "iOS", "React", "native", "WEEX"]
          }
        },
        {
          group: "云计算 / 大数据 / 容器",
          base: {
            title: ["计算机基础",'云计算&大数据'],
            tag: ["Android", "iOS", "React", "native", "WEEX"]
          }
        },
        {
          group: "运维 / 测试 / 数据库",
          base: {
            title: ["运维&测试",'数据库'],
            tag: ["Android", "iOS", "React", "native", "WEEX"]
          }
        },
        {
          group: "UI设计 / 3D动画 / 游戏",
          base: {
            title: ["UI设计&多媒体",'游戏'],
            tag: ["Android", "iOS", "React", "native", "WEEX"]
          }
        },
      ],
      pathTabIndex: 0,
      rankTabIndex: 0,
      itemOnIndex: -1
    };
  },
  mounted() {},
  methods: {
    changePathTabIndex(index) {
      this.pathTabIndex = index;
    },
    changeRankTabIndex(index) {
      this.rankTabIndex = index;
    },
    changeItemOnIndex(index) {
      this.itemOnIndex = index;
    }
  }
};
</script>

<style scoped lang="scss" >
.bjfff {
  box-shadow: 0 2px 8px 0 rgba(7, 17, 27, 0.06);
  background-color: #fff;
}
.bj000 {
  box-shadow: 0 2px 8px 0 rgba(7, 17, 27, 0.06);
}

.r {
  float: right;
}
.l {
  float: left;
}

.container-types.container-recommend {
  padding-top: 0px;
  padding-bottom: 44px;
}
.container-types.container-read {
  padding-bottom: 0;
}

.container-types {
  width: 1152px;
  margin-left: auto;
  margin-right: auto;
  position: relative;
  padding: 36px 0 38px;

  .types-title {
    position: relative;
    font-size: 24px;
    color: #1c1f21;
    letter-spacing: 0px;
    line-height: 26px;

    span {
      font-weight: bold;
      float: left;
    }
    .intro {
      margin-top: 6px;
      margin-left: 12px;
      font-weight: normal;
      font-size: 14px;
      color: #545c63;
      line-height: 20px;
    }
  }
}

.clear {
  clear: both;
}

.main {
  display: block;
  padding: 0;

  .banner-box {
    padding-top: 32px;

    .banner {
      height: 382px;
      width: 1152px;
      background-color: #93999f;
      box-shadow: 0 12px 24px 0 rgba(7, 17, 27, 0.2);
      position: relative;
      overflow: hidden;
      margin: auto;
      margin-bottom: 44px;
      border-radius: 8px;

      .menuwrap {
        height: 382px;
        background-color: rgba(7, 17, 27, 0.5);
        opacity: 0.502;
        position: absolute;
        left: 0px;
        top: 0px;
        width: 216px;
        height: 382px;
        z-index: 1;
      }

      .submenu {
        background: #fff;
        position: absolute;
        left: 216px;
        top: 0px;
        width: 768px;
        height: 382px;
        z-index: 581;
        box-shadow: 0px 4px 8px 0px rgba(0, 0, 0, 0.1);
        box-sizing: border-box;

        .innerBox {
          background-color: #fff;
          padding: 26px 36px 32px;
          position: relative;
          min-height: 150px;
          overflow: hidden;
          box-sizing: border-box;
          .banner-line {
            line-height: 22px;
            margin-bottom: 12px;

            span {
              font-size: 14px;
              color: #1c1f21;
              line-height: 22px;
              font-weight: bold;
            }
          }

          .tag-box {
            font-size: 0;

            a {
              margin-bottom: 16px;
              font-size: 14px;
              line-height: 22px;
              margin-right: 24px;
              display: inline-block;
              color: #1c1f21;
            }
            a:hover {
              color: #f20d0d;
            }
          }
        }
        .recomment-box {
          position: absolute;
          bottom: 0;
          background: #f8fafc;
          padding: 27px 0 0px 36px;

          .banner-course-card {
            width: 312px;
            margin-right: 48px;
            margin-bottom: 27px;

            a {
              display: block;
              width: 100%;
              height: 100%;

              img {
                width: 70px;
                height: 52px;
                border-radius: 4px;
                background-color: #ccc;
              }
              .course-card {
                margin-left: 16px;
                display: inline-block;

                .course-card-name {
                  width: 226px;
                  font-size: 12px;
                  color: #07111b;
                  line-height: 20px;
                  overflow: hidden;
                  text-overflow: ellipsis;
                  white-space: nowrap;
                  font-weight: normal;
                }

                .course-card-price {
                  font-size: 12px;
                  color: #545c63;
                  line-height: 18px;
                }
                .course-card-info {
                  font-size: 12px;
                  color: #545c63;
                  line-height: 18px;
                }
              }
            }
          }
        }
      }

      .menuContent {
        position: relative;
        float: left;
        width: 216px;
        height: 382px;
        z-index: 2;
        padding-top: 17px;
        box-sizing: border-box;
        background: #2b333b;
        font-weight: 400;

        .item {
          height: 50px;
          line-height: 50px;
          padding-left: 12px;
          cursor: pointer;
          position: relative;

          a {
            display: block;
            color: rgba(255, 255, 255, 0.6);
            padding: 0 16px;
            border-top-left-radius: 4px;
            border-bottom-left-radius: 4px;
            height: 50px;
            line-height: 50px;
            transition: all 0.1s;

            .group {
              font-size: 14px;
            }

            i {
              position: absolute;
              right: 8px;
              top: 1px;
              color: rgba(255, 255, 255, 0.5);
              font-size: 12px;
            }
          }
        }

        .item.itemOn {
          a {
            color: #fff;
            background-color: rgba(255, 255, 255, 0.3);
          }
        }
      }

      .banner-content {
        position: relative;
        float: left;
        width: 936px;
        height: 382px;
      }
    }

    .container-types {
      .path-list {
        margin-top: 24px;
        a:first-child {
          margin: 0;
        }
        a {
          float: left;
          margin-left: 18px;
          display: block;
          width: 216px;
          padding-top: 15px;
          height: 65px;
          overflow: hidden;
          transition: all 0.3s;
          background: #f3f5f6;
          border-radius: 8px;
        }

        a:hover {
          box-shadow: 0 3px 8px 0 rgba(0, 0, 0, 0.116);
        }

        i {
          float: left;
          width: 50px;
          height: 50px;
          background: url("../assets/path-2019-9.png") no-repeat;
          background-size: 100%;
          margin-left: 12px;
          margin-right: 10px;
        }
        .i-web {
          background-position: center 0;
        }
        .i-java {
          background-position: center -50px;
        }
        .i-python {
          background-position: center -100px;
        }
        .i-android {
          background-position: center -150px;
        }
        .i-php {
          background-position: center -200px;
        }

        .title {
          font-size: 16px;
          font-weight: bold;
          color: #1c1f21;
          letter-spacing: 1px;
          margin-top: 4px;
        }
        .desc {
          font-size: 12px;
          color: #1c1f21;
          line-height: 16px;
          margin-top: 2px;
          font-weight: 400;
        }
      }
    }
  }
}

.types-content {
  margin-top: 24px;
  margin-left: -24px;
}

.js-path-tab {
  float: left;
  margin-left: 54px;
  font-weight: normal;

  li {
    margin: 0 14px;
    float: left;
    font-size: 14px;
    letter-spacing: 0;
    line-height: 26px;
    cursor: pointer;
    color: #545c63;
  }

  li:hover {
    color: rgb(255, 38, 0);
  }
  .curr {
    color: #f20d0d;
    border-bottom: 2px solid #f20d0d;
  }
}

.js-rank-tab {
  float: left;
  margin-left: 54px;
  font-weight: normal;

  li {
    margin: 0 14px;
    float: left;
    font-size: 14px;
    letter-spacing: 0;
    line-height: 26px;
    cursor: pointer;
    color: #545c63;
  }

  li:hover {
    color: rgb(255, 38, 0);
  }
  .curr {
    color: #f20d0d;
    border-bottom: 2px solid #f20d0d;
  }
}

.more {
  float: right;
  margin-top: 2px;
  line-height: 24px;
  color: #1c1f21;
  font-size: 14px;
  font-weight: normal;

  .iconfont {
    font-size: 10px;
  }
}

.rank-info {
  i {
    font-size: 20px;
    color: #b2b8bd;
    letter-spacing: 3.3px;
    text-align: center;
    line-height: 36px;
    cursor: pointer;
  }
  i:hover + .info {
    display: block;
  }
  .info {
    display: none;
    position: absolute;
    top: 32px;
    right: 0;
    z-index: 9;
    font-size: 12px;
    color: #1c1f21;
    text-align: center;
    line-height: 26px;
    background: #ffffff;
    box-shadow: 0 8px 16px 0 rgba(28, 31, 33, 0.2);
    border-radius: 12px;
    width: 290px;
    height: 200px;
    box-sizing: border-box;
    padding: 35px 20px;
    font-weight: normal;

    dt {
      font-weight: bolder;
    }

    .free {
      border-top: 1px solid rgba(28, 31, 33, 0.1);
      margin-top: 13px;
      padding-top: 13px;
    }
  }
}
</style>
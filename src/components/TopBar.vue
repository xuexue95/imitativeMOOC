<template>
  <div class="topBar">

    <div id="logo">
      <a href>
        <img src="../../public/logo.png" alt />
      </a>
    </div>

    <ul class="nav-item">
      <li>
        <a href>免费课程</a>
      </li>
      <li>
        <a href>实战课程</a>
      </li>
      <li>
        <a href>就业班</a>
      </li>
      <li>
        <a href>专栏</a>
      </li>
      <li>
        <a href>猿问</a>
      </li>
      <li>
        <a href>手记</a>
      </li>
    </ul>

    <div class="login-area">
      <ul>
        <li class="app-download" @mouseenter="showDownloadBox" @mouseleave="showDownloadBox">
          <a href>下载APP</a>
          <div class="app-load-box" :style="{display:AppDisplay}">
            <div class="mobile-load-box">
              <h4>慕课网APP - 随时随地学编程</h4>
              <img src="../../public/appload.png" alt />
              <div class="right">
                <a href class="app-load-btn">
                  <i class="iconfont icon-iphone"></i>
                  App Store下载
                </a>
                <a href class="app-load-btn">
                  <i class="iconfont icon-anzhuo-copy"></i>
                  Android下载
                </a>
                <p>扫描下载慕课网APP</p>
              </div>
            </div>
          </div>
        </li>
        <li class="shop-car">
          <a class="btn">
            <span class="iconfont icon-gouwuche"></span>
            <span>购物车</span>
          </a>
          <div class="my-car">
            <div class="car-title-box">
              <h2>我的购物车</h2>
              <h5 class="right">已加入0门课程</h5>
            </div>
            <div class="car-wrap">
              <span class="iconfont icon-gouwuche"></span>
              <h3>购物车里空空如也</h3>
              <div class="text">快去这里选购你中意的课程</div>

              <a href>实战课程</a>

              <a href>就业班</a>
            </div>
            <div class="goto-mycar">
              <div class="show-box">
                <a href>我的订单中心</a>
                <a href class="go-car right">去购物车</a>
              </div>
            </div>
          </div>
        </li>
        <li class="header-signin">
          <a href>登录</a>
          /
          <a href>注册</a>
        </li>
      </ul>
    </div>

    <div class="search">
      <div class="search-area" :class="{focus:focus}">
        <input
          type="text"
          class="search-input"
          placeholder="请输入想搜索的内容"
          @focus="changeStyle"
          @blur="changeStyle"
        />
      </div>
      <div class="showhide-search" :class="{focus:focus}">
        <i class="iconfont icon-fangdajing"></i>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "TopBar",
  props: {},
  data() {
    return {
      focus: false,
      AppDisplay: "none",
    };
  },
  methods: {
    changeStyle() {
      this.focus = !this.focus;
    },
    
    showDownloadBox() {
      this.AppDisplay == "none"
        ? (this.AppDisplay = "block")
        : (this.AppDisplay = "none");
    },
  }
};
</script>

<style scoped lang="scss">
.right {
  float: right;
}
.left {
  float: left;
}
.topBar {
  width: auto;
  height: 72px;
  box-shadow: 0 4px 8px 0 rgba(7, 17, 27, 0.1);
  padding-right: 10px;
  background: #fff;
      position: relative;

  #logo {
    float: left;
    margin: 0 20px;

    a {
      display: block;
      width: 140px;
      height: 72px;

      img {
        height: 72px;
      }
    }
  }

  .nav-item {
    padding-inline-start: 40px;

    li {
      float: left;

      a {
        color: #4d555d;
        display: block;
        text-align: center;
        padding: 0 20px;
        font: size 16px;
        height: 72px;
        line-height: 72px;
      }

      a:hover {
        color: #000;
      }
    }
  }

  .login-area {
    float: right;

    ul {
      li {
        float: left;

        a:hover {
          color: rgb(255, 38, 0);
        }
      }

      .app-download {
        height: 72px;
        line-height: 72px;
        color: rgba(255, 255, 255, 0.6);
        position: relative;

        a {
          padding: 0 15px;
          font-size: 14px;
          color: #71777d;
        }

        .app-load-box {
          position: absolute;
          right: 0;
          width: 304px;
          padding: 10px 24px 22px;
          box-sizing: border-box;
          background-color: #fff;
          color: #4d555d;
          line-height: 16px;
          box-shadow: 0 8px 16px 0 rgba(7, 17, 27, 0.2);
          border-bottom-right-radius: 8px;
          border-bottom-left-radius: 8px;
          z-index: 99999;
          font-size: 12px;

          .mobile-load-box {
            h4 {
              margin: 12px 0;
              font-size: 14px;
              color: #1c1f21;
              text-align: center;
              line-height: 22px;
            }

            img {
              width: 108px;
              height: 108px;
            }

            .app-load-btn {
              display: block;
              color: #fff;
              width: 132px;
              height: 36px;
              margin-bottom: 8px;
              line-height: 36px;
              background: #4d555d;
              border-radius: 18px;
              box-sizing: border-box;
              font-size: 12px;
            }

            .app-load-btn:hover {
              background: #000;
            }

            p {
              margin-top: 12px;
              text-align: center;
            }
          }
        }
      }

      .shop-car {
        height: 72px;
        position: relative;
        line-height: 72px;

        .btn {
          display: inline-block;
          padding: 0 18px;
          width: auto;
          box-sizing: border-box;
          border-radius: 18px;
          height: 36px;
          line-height: 36px;
          color: #787d82;
          text-align: center;
          border: 1px solid #d9dde1;

          .icon-gouwuche {
            margin-right: 8px;
            font-size: 16px;
          }
        }

        .my-car {
          display: none;
          width: 344px;
          padding: 0 16px;
          position: absolute;
          right: 0;
          top: 54px;
          background: #fff;
          box-sizing: border-box;
          z-index: 99999;
          box-shadow: 0 8px 16px 0 rgba(28, 31, 33, 0.2);
          border-bottom-right-radius: 8px;
          border-bottom-left-radius: 8px;

          .car-title-box {
            padding: 13px 12px;
            border-bottom: 1px solid #ccc;

            h2 {
              font-size: 14px;
              color: #1c1f21;
              font-weight: bold;
              height: 24px;
              line-height: 24px;
              display: inline-block;
            }

            h5 {
              font-size: 12px;
              color: #9199a1;
              height: 24px;
              line-height: 24px;
            }
          }

          .car-wrap {
            height: 284px;
            text-align: center;

            .icon-gouwuche {
              margin: 36px 0 8px;
              display: inline-block;
              font-size: 72px;
              color: #d3d6d9;
            }

            h3 {
              font-size: 14px;
              color: #544c63;
              text-align: center;
              line-height: 24px;
              font-weight: 400;
            }

            .text {
              margin-bottom: 8px;
              font-size: 12px;
              color: #9199a1;
              text-align: center;
              line-height: 24px;
            }

            a {
              display: block;
              color: rgba(240, 20, 20, 0.6);
              font-size: 12px;
              line-height: 24px;
              margin-bottom: 4px;
            }
          }

          .goto-mycar {
            padding: 16px 12px;
            border-top: 1px solid #ccc;

            .show-box {
              height: 32px;
              line-height: 32px;
              font-size: 12px;

              a {
                color: #93999f;
              }

              a:hover {
                color: #000;
              }
              .go-car {
                color: #fff;
                font-size: 12px;
                line-height: 16px;
                padding: 8px 16px;
                background: rgba(240, 20, 20, 0.8);
                border-radius: 16px;
                border: none;
              }
              .go-car:hover {
                background: rgba(226, 0, 0, 0.8);
                color: #fff;
              }
            }
          }
        }
      }

      .shop-car:hover .btn {
        color: rgb(255, 38, 0);
      }
      .shop-car:hover .my-car {
        display: block;
      }
      .header-signin {
        color: #d9dde1;
        margin-left: 12px;

        a {
          color: #4d555d;
          display: inline-block;
          padding: 0 12px;
          height: 72px;
          line-height: 72px;
          font-size: 14px;
          transition: background-color 0.2s;
        }
      }
    }
  }

  .search {
    float: left;
    margin-left: 24px;
    position: relative;

    .search-area {
      border-bottom: 1px solid #d9dde1;

      float: right;
      position: relative;
      height: 46px;
      width: 260px;
      padding-right: 40px;
      transition: width 0.3s;
      margin: 12px 0;

      .search-input {
        padding: 12px 0;
        width: 100%;
        height: 46px;
        line-height: 22px;
        font-size: 12px;
        border: 0;
        box-sizing: border-box;
        outline: none;
      }
    }

    .search-area.focus {
      border-bottom: 1px solid red;
    }

    .showhide-search {
      width: 20px;
      height: 24px;
      text-align: center;
      position: absolute;
      display: inline-block;
      right: 0;
      bottom: 24px;
      padding: 0 8px;
      border-radius: 18px;

      i {
        display: block;
        height: 24px;
        color: #757a7e;
        cursor: pointer;
        font-size: 14px;
        line-height: 24px;
        width: 20px;
        font-weight: bolder;
      }
    }

    .showhide-search.focus {
      background: rgb(243, 186, 186);

      i {
        color: #ec0c0c;
      }
    }

    .showhide-search:hover {
      background: rgb(243, 186, 186);

      i {
        color: #ec0c0c;
      }
    }
  }
}
</style>
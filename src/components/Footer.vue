<template>
  <div class="footer">
    <div class="container">
      <div class="footer-wrap">
        <div class="footer-sns">
          <div class="l">
            <a href class="footer-sns-weixin">
              <i class="footer-sns-weixin-expand"></i>
            </a>
            <p>官方公众号</p>
          </div>
          <div class="l">
            <a href class="footer-sns-weibo" title="新浪微博"></a>
            <p>官方微博</p>
          </div>
        </div>
      </div>
      <div class="footer-link">
        <a href>企业合作</a>
        <a href>人才招聘</a>
        <a href>联系我们</a>
        <a href>讲师招募</a>
        <a href>帮助中心</a>
        <a href>意见反馈</a>
        <a href>慕课大学</a>
        <a href>代码托管</a>
        <a href>友情链接</a>
      </div>
      <div class="footer-copy">
        <img alt="©" src="https://www.imooc.com/static/moco/v1.0/images/face/36x36/a9.png" />
        <p>&nbsp;2019&nbsp;imooc.com&nbsp;&nbsp;京ICP备 12003892号-11 北京奥鹏文化传媒有限公司</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "pageFooter",
  props: {}
};
</script>
<style lang="scss" scoped>
.l {
  float: left;
}

.footer {
  padding: 36px 0;

  .container {
    position: relative;
    width: 1152px;
    margin: 0 auto;

    .footer-wrap {
      position: absolute;
      width: auto;
      right: 0;
      bottom: 0;
      .footer-sns {
        text-align: center;

        .footer-sns-weixin {
          display: inline-block;
          height: 32px;
          width: 32px;
          vertical-align: middle;
          background: url("../assets/idx-btm.png");
          background-repeat: no-repeat;
          margin: 0 9px;
          position: relative;
          background-position: -52px -221px;

          .footer-sns-weixin-expand {
            position: absolute;
            display: none;
            width: 172px;
            height: 212px;
            left: -77px;
            bottom: 40px;
            background: url("../assets/elevator.png");
          }
        }
        .footer-sns-weixin:hover {
          background-position: -52px -262px;
          .footer-sns-weixin-expand {
            display: block;
          }
        }

        .footer-sns-weibo {
          display: inline-block;
          height: 32px;
          width: 32px;
          vertical-align: middle;
          background: url("../assets/idx-btm.png");
          background-repeat: no-repeat;
          margin: 0 9px;
          position: relative;
          background-position: 0 -221px;
        }
        .footer-sns-weibo:hover {
          background-position: 0 -262px;
        }
        p {
          font-size: 12px;
          color: #4d555d;
          line-height: 24px;
          margin-top: 4px;
        }
      }
      .footer-sns div:first-child {
        margin-right: 32px;
      }
    }

    .footer-link {
      text-align: left;
      border: none;
      padding: 0;

      a {
        margin: 0 10px;
        color: #99a1a6;
        font-size: 12px;
      }
      a:hover{
          color:black;
      }
    }

    .footer-copy {
      font-size: 12px;
      line-height: 14px;
      padding: 0;
      padding-left: 10px;
      text-align: left;
      margin-top: 8px;
      color: #93999f;
      line-height: 24px;

      img {
          float: left;
      }
    }
  }
}
</style>
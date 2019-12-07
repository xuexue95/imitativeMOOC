<template>
  <div class="newcomer" :style="{display:show}">
    <a href class="link"></a>
    <i class="close iconfont icon-guanbi" @click.self="close"></i>
  </div>
</template>

<script>
export default {
  name: "NewComer",
  props: {},
  data() {
    return {
      show: "block"
    };
  },
  methods: {
    close() {
      this.show = "none";
    }
  }
};
</script>

<style scoped lang="scss">
.newcomer {
  .link {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 136px;
    background: url("../../public/newcomer.png");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    z-index: 998;
  }
  .close {
    position: fixed;
    right: 20px;
    bottom: 48px;
    font-size: 20px;
    color: rgba(255, 255, 255, 0.6);
    z-index: 999;
  }
  .close:hover {
    color: azure;
  }
}
</style>
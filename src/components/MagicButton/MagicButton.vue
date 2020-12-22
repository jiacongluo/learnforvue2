<template>
  <div class="magic-button">
    <span @click="handleClick">button</span>
  </div>
</template>
<script>
export default {
  name: "MagicButton",
  data() {
    return {};
  },
  props: {},
  components: {},
  created() {},
  mounted() {},
  watch: {},
  computed: {},
  directives: {},
  filter: {},
  methods: {
    handleClick() {
      alert("hello");
    }
  }
};
</script>
<style lang="scss" scoped>
/* @import url(); 引入css类 */
.magic-button {
  /* 弹性布局 让页面元素垂直+水平居中 */
  display: flex;
  justify-content: center;
  align-items: center;
  /* 让页面占屏幕总高 */
  height: 100vh;
  background-color: #000;
}

span {
  /* 相对定位 */
  position: relative;
  width: 400px;
  height: 100px;
  line-height: 100px;
  text-align: center;
  text-transform: uppercase;
  font-size: 24px;
  color: #fff;
  /* 圆角属性 */
  border-radius: 50px;
  /* 背景渐变色 */
  background-image: linear-gradient(
    to right,
    #03a9f4,
    #f441a5,
    #ffeb3b,
    #09a8f4
  );
  /* 背景渐变色大小 */
  background-size: 400%;
  z-index: 1;
}

/* 下面设计 发光效果 */
span::before {
  content: "";
  position: absolute;
  top: -5px;
  bottom: -5px;
  left: -5px;
  right: -5px;
  border-radius: 50px;
  /* 背景渐变色 */
  background-image: linear-gradient(
    to right,
    #03a9f4,
    #f441a5,
    #ffeb3b,
    #09a8f4
  );
  /* 背景渐变色大小 */
  background-size: 400%;
  /* 元素的位置 底层或者顶层  -值表示底层 + 值表示顶层 */
  z-index: -1;
  /* 设置模糊度 显示发光效果 */
  filter: blur(10px);
}

span:hover {
  /* 动画 名称 时间 infinite 是无限次播放 */
  animation: sun 8s infinite;
  cursor: pointer;
}

span:hover::before {
  animation: sun 8s infinite;
}

@keyframes sun {
  100% {
    /* 背景位置 */
    background-position: -400% 0;
  }
}
</style>

<template>
  <div>
    <!-- v-show通过更改style样式实现隐藏与显示 -->
    <p v-show="isShow">我是v-show</p>
    <button @click="btn">显示隐藏</button>

    <br />
    <br />
    <!-- v-if会false会销毁dom元素 -->
    <p v-if="isShow1">我是v-if</p>
    <button @click="btn1">显示隐藏</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
      isShow1: false,
    };
  },
  methods: {
    btn() {
      this.isShow = !this.isShow;
    },
    btn1() {
      this.isShow1 = !this.isShow1;
    },
  },
};
</script>

<style></style>

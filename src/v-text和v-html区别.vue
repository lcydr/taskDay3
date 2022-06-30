<template>
  <div>
    <h1>{{ str }}</h1>

    <!-- 读取html标签 -->
    <h2 v-html="str"></h2>
    <!-- 只读取文本 -->
    <h2 v-text="str"></h2>

    <!-- v-html会覆盖插值表达式 -->
    <h2 v-html="str">{{ 123 }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      str: '<span>123465</span>',
    };
  },
};
</script>

<style></style>

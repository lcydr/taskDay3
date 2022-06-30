<template>
  <div>
    <ul>
      <li v-for="obj in arr" :key="obj">{{ obj }}</li>
    </ul>
    <button @click="btn">点击</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: ['帅哥', '美女', '小朋友'],
    };
  },
  methods: {
    btn() {
      // 头部数据添加到尾部
      this.arr.push(this.arr[0]);
      // 再把头部数据删除掉
      this.arr.shift();
    },
  },
};
</script>

<style></style>

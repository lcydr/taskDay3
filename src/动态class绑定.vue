<template>
  <div>
    <p v-bind:class="{ active: isShow }" class="ppp">我是乒乒乓乓</p>
    <button @click="isShow = !isShow">Click ME</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
    };
  },
  methods: {},
};
</script>

<style>
.active {
  color: red;
}
.ppp {
  border: 10px solid #ccc;
}
</style>

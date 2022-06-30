<template>
  <div>
    <p v-bind:class="{active: activeFlag}" class="ppp">我是乒乒乓乓</p>
    <button @click="activeFlag = !activeFlag">Click ME</button>
  </div>
</template>

<script>
export default {
  name: 'VuecliDemo03Class',

  data() {
    return {
      activeFlag: true
    };
  },

  mounted() {
    
  },

  methods: {
    
  },
};
</script>
<style>
  .active {
    color: red;
  }
  .ppp{
    border: 10px solid #ccc;
  }
</style>

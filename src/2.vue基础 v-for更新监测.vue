<template>
  <div>
        <ul>
      <li v-for="(val, index) in arr" :key="index">
        {{ val }}
      </li>
    </ul>
    <button @click="revBtn">数组翻转</button>
    <button @click="sliceBtn">截取前3个</button>
    <button @click="updateBtn">更新第一个元素值</button>
  </div>
</template>

<script>
export default {
  data(){
    return {
      arr:[1,2,3,4,5]
    }
  },
  methods:{
    revBtn(){ 
      this.arr.reverse()
    },
    sliceBtn(){
      this.arr.splice(3)
    },
    updateBtn(){
      this.$set(this.arr,0,100)
    }
  },
}
</script>

<style>

</style>
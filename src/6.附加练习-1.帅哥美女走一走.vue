<template>
  <div>
    <ul>
      <li v-for="item in arr" :key="item" >{{item}}</li>
    </ul>
    <button @click="btn">走一走</button>
  </div>
</template>

<script>
export default {
  data(){
    return{
      arr:['1','2','3'] 
    }
    
  },
  methods:{
    btn(){
      this.arr.push(this.arr[0])
      this.arr.shift()
    }
  }
}
</script>

<style>

</style>
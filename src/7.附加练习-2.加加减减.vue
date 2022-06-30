<template>
  <div id="app">
    <ul>
      <li v-for="(item, ind) in arr" :key="item">
        <span>{{ item }}</span>
        <button @click="del(ind)">删除</button>
      </li>
    </ul>
    <button @click="add">生成</button>
  </div>
</template>

<script>
export default {
  data(){
    return{
      arr:[1,5,6]
    };
  },
  methods:{
    add(){
      this.arr.push(Math.floor(Math.random() *20))
    },
    del(ind){
      this.srr.splice(ind,1)
    }
  },
}
</script>

<style>

</style>
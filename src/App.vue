<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model="name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model="age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="sex" @change="getSex">
        <option :value="obj.id" v-for="obj in list" :key="obj.id">{{obj.name}}</option>
      </select>
    </div>
    <div>
      <button @click="add" >添加/修改</button>
    </div>
    <div>
      <table
        border="1"
        cellpadding="10"
        cellspacing="0"
      >
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="(item, index) in arr" :key="index">
          <td>{{index +1}}</td>
          <td>{{item.name}}</td>
          <td>{{item.age}}</td>
          <td>{{item.sex}}</td>
          <td>
            <button @click="btnDelete(index)">删除</button>
            <button @click="btnEdit(index)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data(){
    return {
      name:'',
      age:0,
      arr: [
        { name:'张三',age:10,sex:'男'},
        { name:'李四',age:20,sex:'女'}
      ],
      list: [
        {id:'男',name:'男'},
        {id:'女',name:'女'}
      ],
    }
  },
  created(){
      this.sex = this.list[0].id
    },
    // 获取select选择
  methods:{
    getSex(){
      console.log(this.sex)
    },
    // 添加
    add(){
      if(this.name.trim().length === 0 || this.age === 0) return alert('请输入完整信息')
    this.arr.push({
      index: this.index+1,
      name: this.name, 
      age: this.age,
      sex: this.sex,
    })
      this.name=""
      this.age=0
    },
    btnDelete(ind){
    //  let index = this.arr.findIndex(obj => obj.index == id);
     this.arr.splice(ind,1)
    },
    btnEdit(index){

      this.name =this.arr[index].name
      this.age =this.arr[index].age
      this.sex = this.arr[index].age
      add()
    }
  }
}
</script>

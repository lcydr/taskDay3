<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" v-model.trim="name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" v-model.trim="age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="sex">
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click.prevent="btn">添加/修改</button>
    </div>
    <div>
      <table border="1" cellpadding="10" cellspacing="0">
        <tr>
          <th>序号</th>
          <th>姓名</th>
          <th>年龄</th>
          <th>性别</th>
          <th>操作</th>
        </tr>
        <tr v-for="(obj, index) in arr" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ obj.name }}</td>
          <td>{{ obj.age }}</td>
          <td>{{ obj.sex }}</td>

          <td>
            <button @click="del(index)">删除</button>
            <button @click="dif(index)">编辑</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: '',
      age: 0,
      sex: '',
      list: {},
      arr: [],
      isTure: true,
      indexs: 0,
    };
  },
  methods: {
    dif(id) {
      this.isTure = false;
      this.indexs = id;
      this.name = this.arr[id].name;
      this.age = this.arr[id].age;
      this.sex = this.arr[id].sex;
    },
    btn() {
      if (this.isTure) {
        if (this.name === '' || this.age === 0 || this.sex === '')
          return alert('Please enter');
        this.list = {
          name: this.name,
          age: this.age,
          sex: this.sex,
        };
        // console.log(this.list);
        this.arr.push(this.list);
        // console.log(this.arr);
        this.name = '';
        this.age = 0;
        this.sex = '';
      } else {
        this.arr[this.indexs].name = this.name;
        this.arr[this.indexs].age = this.age;
        this.arr[this.indexs].sex = this.sex;

        // console.log(this.arr);
        // console.log(this.isTure);
        this.isTure = true;
        this.name = '';
        this.age = 0;
        this.sex = '';
      }
    },
    del(id) {
      // console.log(id);
      this.arr.splice(id, 1);
    },
  },
};
</script>

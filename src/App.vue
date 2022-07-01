<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" placeholder="请输入姓名" v-model.trim="name" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" placeholder="请输入年龄" v-model.trim="age" />
    </div>
    <div>
      <span>性别:</span>
      <select v-model="sex">
        <option value="1">男</option>
        <option value="0">女</option>
      </select>
    </div>
    <div>
      <button @click.prevent="addFn">{{ isEdit ? '修改' : '添加' }}</button>
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
        <tr v-for="item in list" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.age }}</td>
          <td>{{ { 0: '女', 1: '男' }[item.sex] }}</td>
          <td>
            <button @click.prevent="del(item.id)">删除</button>
            <button @click="editFn(item)">编辑</button>
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
      list: [
        { id: 1, name: '张三', age: '12', sex: '1', operation: '叉车' },
        { id: 2, name: '李四', age: '21', sex: '1', operation: '垃圾车' },
      ],
      name: '',
      age: '',
      sex: 0,
      isEdit: false,
      currentId: '',
    };
  },
  methods: {
    addFn() {
      if (this.isEdit) {
        const index = this.list.findIndex((ele) => ele.id == this.currentId);
        this.list[index].name = this.name;
        this.list[index].age = this.age;
        this.list[index].sex = this.sex;
        this.currentId = '';
        this.isEdit = false;
        this.clearEdit();
        alert('修改完成');
        return;
      }
      if (this.name == '' || this.age == '') {
        return alert('Please enter');
      }
      const id = this.list[this.list.length - 1]
        ? this.list[this.list.length - 1].id + 1
        : 100;
      this.list.push({
        id,
        name: this.name,
        age: this.age,
        sex: this.sex,
      });
      this.clearEdit();
    },
    editFn(data) {
      this.isEdit = true;
      this.name = data.name;
      this.age = data.age;
      this.sex = data.sex;
      this.currentId = data.id;
    },
    del(id) {
      const index = this.list.findIndex((ele) => {
        return id == ele.id;
      });
      console.log(index);
      this.list.splice(index, 1);
    },
    clearEdit() {
      this.name = '';
      this.age = '';
      this.sex = 0;
    },
  },
};
</script>

<template>
  <div id="app">
    <div>
      <span>姓名:</span>
      <input type="text" />
    </div>
    <div>
      <span>年龄:</span>
      <input type="number" />
    </div>
    <div>
      <span>性别:</span>
      <select>
        <option value="男">男</option>
        <option value="女">女</option>
      </select>
    </div>
    <div>
      <button @click.prevent="addFn">添加/修改</button>
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
          <td>{{ item.sex }}</td>
          <td>{{ item.operation }}</td>
          <td>
            <button @click.prevent="del(item.id)">删除</button>
            <button>编辑</button>
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
        { id: 1, name: '张三', age: '12', sex: '男', operation: '叉车' },
        { id: 2, name: '李四', age: '21', sex: '男', operation: '垃圾车' },
      ],
      name: '',
      age: 0,
    };
  },
  methods: {
    addFn() {
      if (this.name == '' || this.age == 0) alert('Please enter');
      const id = this.list[this.list.length - 1]
        ? this.list[this.list.length - 1].id + 1
        : 100;
      this.list.push({
        id,
        name: this.name,
        age: this.price,
      });
      this.name = '';
      this.age = 0;
    },
    del(id) {
      const index = this.list.findIndex((ele) => {
        return id == ele.id;
      });
      console.log(index);
      this.list.splice(index, 1);
    },
  },
};
</script>

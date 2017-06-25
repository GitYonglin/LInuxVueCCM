<template>
  <div>
    <div class="opeartion">
      <div style="float:left;">
        <el-button size="small" type="primary" @click="routePush('/foods/edit')">添加食材</el-button>
      </div>
      <div style="float:right;">
        <el-select size="small" v-model="value8" filterable placeholder="请选择">
          <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value">
          </el-option>
        </el-select>
      </div>
    </div>
    <div>
    <el-table :data="tableData5" style="width: 100%" ref="multipleTable">
      <el-table-column label="图片" inline-template width="86">
        <template>
          <img :src="row.imgUrl" alt="没有图片">
        </template>
      </el-table-column>
      <el-table-column label="ID" prop="id" width="50"></el-table-column>
      <el-table-column label="名称" prop="name"></el-table-column>
      <el-table-column inline-template label="价格" width="100">
        <el-input-number v-model="row.price" :controls="false"></el-input-number>
      </el-table-column>
      <el-table-column inline-template label="库存" width="100">
        <el-input-number v-model="row.number" :controls="false"></el-input-number>
      </el-table-column>
      <el-table-column inline-template label="上架" width="80">
        <el-checkbox v-model="row.shelves" :controls="false"></el-checkbox>
      </el-table-column>
      <el-table-column inline-template label="销量">
        <el-tag type="success">{{row.sales}}</el-tag>
      </el-table-column>
      <el-table-column label="操作">
        <template scope="scope">
          <el-button size="small" icon="edit"></el-button>
          <el-button size="small" icon="delete"></el-button>
        </template>
      </el-table-column>
    </el-table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'foodCategory',
  data() {
    return {
      msg: '食材概览',
      options: [{
        value: '选项1',
        label: '黄金糕'
      }, {
        value: '选项2',
        label: '双皮奶'
      }, {
        value: '选项3',
        label: '蚵仔煎'
      }, {
        value: '选项4',
        label: '龙须面'
      }, {
        value: '选项5',
        label: '北京烤鸭'
      }],
      value8: '',
      tableData5: [],
      tab5: [{
        id: '1',
        name: '好滋好味鸡蛋仔',
        imgUrl: 'http://element.eleme.io/static/hamburger.50e4091.png',
        price: 99,
        number: 999,
        shelves: true,
        sales: 9999
      }, {
        id: '2',
        name: '好滋好味鸡蛋仔',
        imgUrl: 'http://element.eleme.io/static/hamburger.50e4091.png',
        price: 99,
        number: 999,
        shelves: true,
        sales: 9999
      }, {
        id: '3',
        name: '好滋好味鸡蛋仔',
        imgUrl: 'http://element.eleme.io/static/hamburger.50e4091.png',
        price: 99,
        number: 999,
        shelves: true,
        sales: 9999
      }, {
        id: '4',
        name: '好滋好味鸡蛋仔',
        imgUrl: 'http://element.eleme.io/static/hamburger.50e4091.png',
        price: 99,
        number: 999,
        shelves: true,
        sales: 9999
      }]
    }
  },
  methods: {
    routePush(url) {
      this.$router.push(url)
    }
  },
  beforeMount: function () {
    console.log('3-beforeMount 挂载之前')
    this.tableData5 = this.tab5
  }
}
</script>

<style lang="scss" scoped>
.opeartion {
  margin-bottom: 15px;
  overflow: hidden;
}
</style>

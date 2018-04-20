<template>
  <div class="hello">
    <el-row :gutter="10">
      
      <el-col :span="8" id="el-col-table">
        <el-tabs v-model="activeName" @tab-click="handleClick">
          <el-tab-pane label="商品消息" name="first">
            <el-table :data="selectedGoods" style="width: 100%" border>
              <el-table-column prop="goodsName" label="商品名称"></el-table-column>
              <el-table-column prop="price" label="商品价格"></el-table-column>
              <el-table-column prop="count" label="商品数量"></el-table-column>
              <el-table-column label="操作">
                <template scope="scope">
                  <el-button type="success" size="mini" @click="addGoods(scope.row)">增加</el-button>
                  <el-button type="danger" size="mini" @click="reduceGoods(scope.row)">减少</el-button>
                </template>
              </el-table-column>
            </el-table>
          </el-tab-pane>
          <el-tab-pane label="配置管理" name="second">配置管理</el-tab-pane>
        </el-tabs>
      </el-col>
      
      <el-col :span="16">
        <div class="title">商品选择</div>
        <div class="often-goods">
          <ul>
            <li v-for="goods in oftenGoods" @click="handleGoodsTagClick(goods)">
              <span>{{goods.goodsName}}</span>
              <span>￥：{{goods.price}} 元</span>
            </li>
          </ul>
        </div>
        <div class="tab-goods">
        
        </div>
      </el-col>
    
    </el-row>
  </div>
</template>

<script>
  import axios from "axios"
  
  export default {
    name: 'HelloWorld',
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
        activeName: "first",
        selectedGoods: [],
        oftenGoods: []
      }
    },
    methods: {
      handleClick(tab, event) {
        console.log(tab);
        console.log(event);
      },
      addGoods(row) {
      
      },
      reduceGoods(row) {
      
      },
      handleGoodsTagClick(goods) {
        console.log(goods);
      }
    },
    
    mounted() {
      let height = document.body.clientHeight;
      let tabs = document.getElementById("el-col-table");
      tabs.style.height = height + "px";
    },
    created() {
      axios.get("http://jspang.com/DemoApi/oftenGoods.php").then(response => {
        this.oftenGoods = response.data;
      }).catch(error => {
        console.log(error);
      })
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #el-col-table {
    border-right: 1px solid lightslategray;
  }
  
  .title {
    font-size: 18px;
    border-bottom: 1px solid lightslategray;
  }
  
  .tab-goods {
    width: 100%;
    height: 65%;
  }
  
  .often-goods ul li {
    float: left;
    list-style: none;
    padding: 5px;
    margin: 5px;
    background-color: lightskyblue;
    border: 1px solid lightslategray;
    border-radius: 5px;
  }
</style>

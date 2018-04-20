<template>
  <div class="left-menu">
    <ul>
      <li>
        <i class="icon iconfont icon-iconfont5"></i>
        <div>icon-iconfont5</div>
      </li>
      <li>
        <i class="icon iconfont icon-gouwuche"></i>
        <div>购物车</div>
      </li>
      <li>
        <i class="icon iconfont icon-gouwuchetianjia"></i>
        <div>购物车添加</div>
      </li>
      <li>
        <i class="icon iconfont icon-cuowu"></i>
        <div>错误</div>
      </li>
      <li>
        <i class="icon iconfont icon-jushoucang"></i>
        <div>聚收藏</div>
      </li>
      <li>
        <i class="icon iconfont icon-lajixiang"></i>
        <div>垃圾箱</div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "LeftMenu"
  }
</script>

<style scoped>
  .left-menu {
    width: 5%;
    height: 100%;
    background-color: lightslategray;
    float: left;
    font-size: 10px;
    color: white;
  }
  
  .left-menu ul {
    width: 100%;
    margin: 0;
    padding: 0;
  }
  
  .left-menu ul li {
    text-align: center;
    list-style: none;
    width: 100%;
    padding-top: 10px;
    padding-bottom: 10px;
    margin: 0;
    border-bottom: 1px solid lightslategrey;
  }
</style>

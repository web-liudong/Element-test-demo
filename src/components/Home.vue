<template>
    <div>
     <i class="el-icon-edit"></i>
     <i class="el-icon-share"></i>
     <i class="el-icon-delete"></i>
     <i class="el-icon-search"></i>
     <i class="el-icon-user"></i>
     <i class="el-icon-s-tools"></i>
     <i class="el-icon-phone-outline"></i>
     <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
  <el-menu-item index="1" style="margin-left:30px;">个人中心</el-menu-item>
  <el-submenu index="2" style="margin-left:30px;">
    <template slot="title">我的工作台</template>
    <el-menu-item index="2-1">读书</el-menu-item>
    <el-menu-item index="2-2">敲代码</el-menu-item>
    <el-menu-item index="2-3">音乐</el-menu-item>
    <el-submenu index="2-4">
      <template slot="title">语言</template>
      <el-menu-item index="2-4-1">JavaScript</el-menu-item>
      <el-menu-item index="2-4-2">Java</el-menu-item>
      <el-menu-item index="2-4-3">C++</el-menu-item>
    </el-submenu>
  </el-submenu>
  <el-menu-item index="3" style="margin-left:30px;">消息中心</el-menu-item>
  <el-menu-item index="4" style="margin-left:30px;"><a href="https://www.ele.me" target="_blank">信息管理</a></el-menu-item>
  <el-menu-item index="5" style="margin-left:30px;"><a href="https://www.baidu.com" target="_blank">查询中心</a></el-menu-item>
  <el-menu-item index="7" style="margin-left:30px;"><a href="https://www.sina.com" target="_blank">新闻中心</a></el-menu-item>
  <el-menu-item index="8" style="margin-left:30px;"><a href="https://www.youku.com" target="_blank">影视中心</a></el-menu-item>
  <el-menu-item index="9" style="margin-left:30px;"><a href="https://www.kugou.com" target="_blank">音乐中心</a></el-menu-item>
  <el-menu-item index="10" style="margin-left:30px;"><a href="https://www.book.com" target="_blank">学习中心</a></el-menu-item>
</el-menu>
     
   <el-card class="box-card">
  <div slot="header" class="clearfix">
    <span>催人前进</span>
    <el-button style="float: right; padding: 3px 0" type="text">操作按钮</el-button>
  </div>
  <div v-for="o in item" :key="o" class="text item">
    {{o.name}}
   
  </div>
</el-card>
     
     <h2 style="text-align:center;font-size:12px;">开启你的学习之路：学习进度</h2>
<el-progress :text-inside="true" :stroke-width="24" :percentage="100" status="success"></el-progress>

   <el-calendar v-model="value">
</el-calendar>
<div class="block">
  <span class="demonstration">评个分呗！</span>
  <el-rate 
    v-model="value2"
    :colors="colors">
  </el-rate>
</div>
    <el-tooltip class="item1" effect="dark" content="谢谢" placement="top-start">
      <el-button>感谢你的支持！</el-button>
    </el-tooltip>

   <router-link to="./home"></router-link>
   <router-link to="./about"></router-link>
   <router-view></router-view>

    </div>
</template>

<script>
    export default {
        data() {
            return {
               item:
                   [
                      {name:'每个人都有潜在的能量，只是很容易：被习惯所掩盖，被时间所迷离，被惰性所消磨。'},
                      {name:'喜欢跑步的人很多，但天天跑步的人不多，拥有梦想的人很多，但坚持梦想的人不多。'},
                      {name:'人生最大的悲哀不是失去太多，而是计较太多，这也是导致一个人不快乐的重要原因。'},
                      {name:'对于勇士来说，贫病、困窘、责难、诽谤、冷嘲热讽……，一切压迫都是前进的动力。'},
                      {name:'假如樵夫害怕荆棘，船只避忌风浪，铁匠畏惧火星，那么，世界就会变成另一副模样。'},
                      {name:'只有一条路不能选择——那就是放弃的路；只有一条路不能拒绝——那就是成长的路。'},
                      {name:'成功的第一个条件就是要有决心；而决心要不得迅速干脆果断又必须具有成功的信心。'},
                      {name:'只有满怀自信的人，才能在任何地方都怀有自信地沉浸在生活中，并实现自己的意志。'},
                      {name:'你凭什么认为你一努力就能超过别人，这样岂不是对那些一直努力的人来说很不公平。'},
                   ],
                   value:new Date(),
                   value1:null,
                   value2:null,
                   colors:['#99A9BF', '#F7BA2A', '#FF9900']
               
            }
        },
        methods: {
           
        },
    }
</script>

<style  scoped>
  .el-menu-demo a{
      text-decoration: none;
  }
  .item{
      font-size: 14px;
      color: gray;
  }
  .item:hover{
      color: black;
      font-size: 16px;
  }
  .box-card{
      margin-bottom: 30px;
  }
  .block{
      margin-left: 20px;
  }
  .item1{
      margin-top:10px;
      margin-left: 500px;
      
  }
  .item{
      margin-left: 250px;
      margin-top: 10px;
  }
  .el-icon-edit{
   margin-left: 1070px;
  
  }
</style>
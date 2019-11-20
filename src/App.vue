<template>
  <div id="app">
    
    <router-link to="/home"  class="text">首页</router-link>
    <router-link to="/about" class="text">个人中心</router-link>
   
   
     <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
     
    }
  },
  methods: {
   

  }
}
</script>

<style>
 .text{
   color:gray;
   margin-left: 20px;
   text-decoration: none;
 }
.text:hover{
   color: #409EFF;
}
</style>

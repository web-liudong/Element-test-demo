<template>

    <div>
     <el-progress :text-inside="true" :stroke-width="26" :percentage="100" class="progress_main"></el-progress>
    
    
    
    <el-switch class="title" 
  v-model="value1"
  active-text="开启好心情"
  inactive-text="关闭好心情">
    
</el-switch>
 <div class="block">
    <span class="demonstration"></span>
    <el-carousel height="200px">
      <el-carousel-item v-for="item in 4" :key="item">
        <h3 class="small"></h3>
      </el-carousel-item>
    </el-carousel>
  </div>
    <el-button class="btn_main"
    plain
    @click="open1">
    帮助
  </el-button>
     
      <el-table
      :data="tableData"
      style="width: 100%;">
      <el-table-column
        prop="date"
        label="日期"
        width="180">
      </el-table-column>
      <el-table-column
        prop="name"
        label="书名"
        width="180">
      </el-table-column>
      <el-table-column
        prop="address"
        label="简介">
      </el-table-column>
    </el-table>

     <h3 class="h3_main1">特性</h3>
    <el-collapse v-model="activeNames" @change="handleChange" class="collapse_main">
  <el-collapse-item title="一致性 Consistency" name="1">
    <div>与现实生活一致：与现实生活的流程、逻辑保持一致，遵循用户习惯的语言和概念；</div>
    <div>在界面中一致：所有的元素和结构需保持一致，比如：设计样式、图标和文本、元素的位置等。</div>
  </el-collapse-item>
  <el-collapse-item title="反馈 Feedback" name="2">
    <div>控制反馈：通过界面样式和交互动效让用户可以清晰的感知自己的操作；</div>
    <div>页面反馈：操作后，通过页面元素的变化清晰地展现当前状态。</div>
  </el-collapse-item>
  <el-collapse-item title="效率 Efficiency" name="3">
    <div>简化流程：设计简洁直观的操作流程；</div>
    <div>清晰明确：语言表达清晰且表意明确，让用户快速理解进而作出决策；</div>
    <div>帮助用户识别：界面简单直白，让用户快速识别而非回忆，减少用户记忆负担。</div>
  </el-collapse-item>
  <el-collapse-item title="可控 Controllability" name="4">
    <div>用户决策：根据场景可给予用户操作建议或安全提示，但不能代替用户进行决策；</div>
    <div>结果可控：用户可以自由的进行操作，包括撤销、回退和终止当前操作等。</div>
  </el-collapse-item>
</el-collapse>
  <h3 class="h3_main">书签</h3>
  <el-radio-group v-model="direction" class="radio_main">
  <el-radio label="ltr">从左往右开</el-radio>
  <el-radio label="ttb">从上往下开</el-radio>
</el-radio-group>

<el-button @click="drawer = true" type="primary" style="margin-left: 16px;margin-top:20px;">
  点我打开
</el-button>
   <el-drawer
  title="Vue.js"
  :visible.sync="drawer"
  :direction="direction"
  :before-close="handleClose">
  <span>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式框架。与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用提供驱动。</span>
</el-drawer>


<div class="block_main">
  <span class="demonstration">评个分呗！</span>
  <el-rate 
    v-model="value2"
    :colors="colors">
  </el-rate>
</div>
    <el-tooltip class="item1" effect="dark" content="谢谢" placement="top-start">
      <el-button>感谢你的支持！</el-button>
    </el-tooltip>

    </div>
       
</template>

<script>
    export default {
        data() {
          return {
            value1:true,
               tableData: [{
            date: '2019-05-02',
            name: 'CSS权威指南',
            address: ' 资深CSS专家Eric A.Meyer。利用他独有的睿智和丰富的经验对属性、标记、标记属性和实现做了深入的研究，另外在浏览器支持和设计原则等实际问题上也有独到的见解。你所需要的就是HTML 4.0的知识即可以为网站布局和分页创建简明而且易于维护的脚本，同时兼具桌面系统的美观性和可控性。'
          }, {
            date: '2019-05-04',
            name: 'JavaScript高级程序设计',
            address: 'Nicholas C.Zakas世界知名的JavaScript专家和Web开发人员。Nicholas拥有丰富的Web开发和界面设计经验，曾经参与许多世界大公司的Web解决方案开发，并与他人合作撰写了畅销书《Ajax高级程序设计》。'
          }, {
            date: '2019-05-01',
            name: 'WEB性能权威指南',
            address: '《Web性能权威指南》适合所有Web应用及站点开发人员阅读，包括但不限于前端、后端、运维、大数据分析、UI/UX、存储、视频、实时消息，以及性能工程师。'
          }, {
            date: '2019-05-03',
            name: '算法导论',
            address: '在有关算法的书中，有一些叙述非常严谨，但不够全面；另一些涉及了大量的题材，但又缺乏严谨性。本书将严谨性和全面性融为一体，深入讨论各类算法，并着力使这些算法的设计和分析能为各个层次的读者接受。全书各章自成体系，可以作为独立的学习单元；算法以英语和伪代码的形式描述，具备初步程序设计经验的人就能看懂；说明和解释力求浅显易懂，不失深度和数学严谨性。'
          },
            {
            date: '2019-11-03',
            name: '程序员的自我修养',
            address: '程序员作为一个职业、也作为一个群体，正逐渐从幕后走向前台，并以他们自己的能力加速改变着世界，也改变着人们生活的方方面面。然而，对于程序员，特别是年轻程序员们来说，如何理解自己的职业与发展，如何看待自己的工作与生活，这些问题往往比那些摆在面前的技术难题更让他们难以解答。'
          },
          ],
           drawer: false,
           direction: 'rtl',
           value2: null,
           colors: ['#99A9BF', '#F7BA2A', '#FF9900'] 
          }
        },
        methods: {
         open1() {
        const h = this.$createElement;

        this.$notify({
          title: '代码ing!',
          message: h('i', { style: 'color: teal'}, '这是本人个人学习,交流的文档,这是本人个人学习,交流的文档,这是本人个人学习,交流的文档,重要的事情说三遍!')
        });
        },
         handleClose(done) {
        this.$confirm('确认关闭？')
          .then(_ => {
            done();
          })
          .catch(_ => {});
      }
    }
    }
</script>

<style  scoped>
   .title{
     margin-top: 20px;
     margin-bottom: 10px;
     margin-left: 20px;
   }
   .progress_main{
     margin-top: 20px;
   }
  .btn_main{
    margin-top: 10px;
    margin-left: 1150px;
   
  }
   .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
  }

  .el-carousel__item:nth-child(2n) {
    background-image: url(https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg)
  }
  
  .el-carousel__item:nth-child(2n+1) {
     background-color: #67C23A;
  }
  .collapse_main{
    margin-top: 20px;
  }
  .h3_main{
    font-weight: 400;
    color: #67C23A;
  }
  .h3_main1{
    font-weight: 400;
    color: #67C23A;
    margin-left: 1000px;
  }
  .block_main{
    margin-left: 1100px;
  }
  .item1{
    margin-top: 10px;
    margin-left: 600px;
  }
</style>
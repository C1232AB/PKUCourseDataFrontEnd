<template>
    
<div>
<el-container style="height: 500px; border: 1px solid #eee">
  <el-container>
    <el-header style="text-align: right; font-size: 12px">
      <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
  <el-row justify="space-around" type="flex">
    <router-link to = "home"><el-menu-item index="1">首页</el-menu-item></router-link>
      <router-link to="Taglist"><el-menu-item index="3" >标签列表</el-menu-item></router-link>
    <el-menu-item index="4">个人空间</el-menu-item>
    <el-row justify="space-around" type="flex" :gutter="2">
      <el-menu-item index="5" >
        <el-col :span="100">
          <el-input v-model="input" placeholder="搜索你想要的资料">
          </el-input>
      </el-col>
      </el-menu-item>
      <el-menu-item index="6" >
       <el-col :span="2">
          <div class="grid-content bg-purple">
            <router-link to="Result">
              <el-button>search</el-button>
           </router-link>
         </div>
       </el-col>
      </el-menu-item>
    </el-row>
  </el-row>
</el-menu>
      
    </el-header>
    
    <el-main>
      <el-table :data="tableData">
        <el-table-column prop="date" label="日期" width="140">
        </el-table-column>
        <el-table-column prop="contributer" label="发布者" width="120">
        </el-table-column>
        <el-table-column prop="tag" label="标签" width=200>
          <el-tag>标签一</el-tag>
          <el-tag type="success">标签二</el-tag>
        </el-table-column>
        <el-table-column prop="intro" label="简介" width="700">
        </el-table-column>
        <el-table-column prop="Details" label="详细情况" width="70">
              <el-link type="primary">details</el-link>
        </el-table-column>
      </el-table>
    </el-main>
  </el-container>
</el-container>
</div>
</template>>

<script>
  export default {
    data() {
      const item = {
        date: '11.11 18:00',
        contributer: 'Nano',
        tag: 'Null',
        intro: 'blank'
      };
      return {
        tableData: Array(20).fill(item)
      }
    }
  };
</script>

<style>
  .el-header {
    background-color: rgb(253, 253, 251);
    color: rgb(14, 13, 13);
    line-height: 60px;
  }
  
  .el-aside {
    color: #333;
  }
</style>


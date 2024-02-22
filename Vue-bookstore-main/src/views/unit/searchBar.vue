<template>
  <el-row style="text-align: center">
      <el-col :span="24">
          <el-form :inline="true">
              <el-form-item @click="goHome">
                 <img src="https://pic.616pic.com/ys_bnew_img/00/17/22/5d5gXTcXh3.jpg" style=" width:40px; height:40px;"/>
              </el-form-item>
              <el-form-item>
                  <el-input v-model="keyword"
                            placeholder="请输入关键字"
                            size="large"/>
              </el-form-item>
              <el-form-item>
                  <el-button type="primary"
                             @click="handleSearch(keyword)">搜索</el-button>
              </el-form-item>
          </el-form>
      </el-col>
  </el-row>
</template>

<script setup>
import { ref } from 'vue'
import router from '@/router'

const keyword=ref('')


const handleSearch=(keyword)=>{
  router.push({
    path:'searchpage',
    query:{
      keyword:keyword
    }
  })
  keyword=''
}
const goHome=()=>{
  router.push('/')
}
  
</script>

<style scoped>

</style>
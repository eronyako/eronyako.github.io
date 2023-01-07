<script setup>
import { RouterView } from 'vue-router'
import TopNav from './components/TopNav.vue'
import Footer from './components/Footer.vue'
import Data from '@/assets/data/data.json'
import {provide, ref} from "vue";

const jsonData = Data
const path = ref('/')

// 使用 provide 给下级组件提供数据
provide('navData',jsonData.nav)

</script>

<template>

  <div class="common-layout">
    <el-container>
      <el-header>
        <!-- 使用 props 父传子 -->
        <TopNav :navData="jsonData.nav"></TopNav>
      </el-header>
      <el-container>
          <el-main class="page-content">
            <RouterView />
          </el-main>
          <el-footer>
            <Footer></Footer>
          </el-footer>
      </el-container>
    </el-container>
    <el-backtop :right="50" :bottom="50" />
  </div>


</template>

<style scoped>
.page-content {
  width: 60%;
  margin: auto;
}
@media screen and (max-width: 1920px) {
  .page-content {
    width: 70%;
  }
}
@media screen and (max-width: 1000px) {
  .page-content {
    width: 80%;
  }
}
</style>

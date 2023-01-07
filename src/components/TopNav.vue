<script setup>
import {OfficeBuilding} from '@element-plus/icons-vue'
const handleSelect = (key, keyPath) => {
  console.log(key, keyPath)
}
const props = defineProps(['navData'])

</script>

<template>
  <el-menu :router="true" class="el-menu-demo" mode="horizontal" :ellipsis="false" @select="handleSelect">
    <el-menu-item index="/"><el-icon :size="56"><OfficeBuilding /></el-icon></el-menu-item>
    <div class="flex-grow" />
    <el-menu-item v-for="(value,key) in props.navData" :key="key" :index="value.path">
      {{ value.name }}
    </el-menu-item>
  </el-menu>
</template>

<style scoped>
.flex-grow {
  flex-grow: 1;
}
</style>
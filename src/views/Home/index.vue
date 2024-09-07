<script setup>
import RealTimeImageTopic from './components/RealTimeImageTopic.vue'
</script>

<template>
  <el-container>
    <el-aside>
      <MusicPlayer></MusicPlayer>
    </el-aside>
    <el-container>
      <el-main style="padding: 10px">
        <RealTimeImageTopic></RealTimeImageTopic>
      </el-main>
      <el-footer>Footer</el-footer>
    </el-container>
    <el-aside>Aside</el-aside>
  </el-container>
</template>

<style scoped lang="scss"></style>

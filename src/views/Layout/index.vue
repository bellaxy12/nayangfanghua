<script setup></script>

<template>
  <div class="common-layout">
    <el-container>
      <el-header class="header" height="210px"> </el-header>
      <div class="nav">
        <el-menu
          style="justify-content: space-around"
          default-active="1"
          class="el-menu"
          mode="horizontal"
        >
          <el-menu-item index="1">首页</el-menu-item>
          <el-sub-menu index="2">
            <template #title>歌曲库</template>
            <el-menu-item index="2-1">item one</el-menu-item>
            <el-menu-item index="2-2">item two</el-menu-item>
            <el-menu-item index="2-3">item three</el-menu-item>
          </el-sub-menu>
          <el-menu-item index="4">视频库</el-menu-item>
          <el-menu-item index="5">文章库</el-menu-item>
          <el-menu-item index="6">现场演出库</el-menu-item>
          <el-menu-item index="7">综艺访谈库</el-menu-item>
          <el-menu-item index="8">媒体报道库</el-menu-item>
          <el-menu-item index="9">贝娜年表</el-menu-item>
          <el-menu-item index="10">纪念贝娜</el-menu-item>
          <el-menu-item index="11">贝壳天地</el-menu-item>
          <el-menu-item index="12">器官捐献</el-menu-item>
          <el-menu-item index="13">网络资源</el-menu-item>
          <el-menu-item index="14">歌迷后援会</el-menu-item>
        </el-menu>
      </div>
      <el-main>
        <router-view></router-view>
      </el-main>
    </el-container>
  </div>
</template>

<style scoped>
.common-layout {
  width: 100%;
  height: 100%;
  .header {
    background-image: url('@/assets/images/header1.jpeg');
    background-size: cover;
    border-radius: 20px;
    margin-bottom: 10px;
  }
  .nav {
    margin-bottom: 10px;
    .el-menu {
      border-radius: 10px;
    }
    .el-menu > * {
      padding: 5px;
    }
  }
}
</style>

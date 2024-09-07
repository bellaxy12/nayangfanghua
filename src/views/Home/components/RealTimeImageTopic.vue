<script setup>
const imgUrl = 'http://www.yaobella.com/photo/picture/172380837831/photo_1723809410691_'
</script>

<template>
  <div class="image-topic">
    <div class="image-topic-header">
      <span class="image-topic-header-title">图片专题 - 2024年8月11日贝娜新家风景</span>
      <div class="image-topic-header-more">more</div>
    </div>
    <el-carousel height="300px" type="card" motion-blur>
      <el-carousel-item v-for="item in 10" :key="item">
        <img :src="imgUrl + (item - 1) + '.jpg'" alt="" />
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<style scoped lang="scss">
.image-topic {
  padding: 10px;
  border: 3px solid #fb88b8;
  border-radius: 20px;
  &-header {
    display: flex;
    justify-content: space-between;
    &-title {
      display: block;
      font-size: 20px;
      // 上移10px
      margin-bottom: 10px;
      // 居中
    }
    &-more {
      width: 50px;
      height: 18px;
      text-align: center;
      line-height: 18px;
      border-radius: 9px;
      background-color: #fb88b8;
      cursor: pointer;
    }
  }
  img {
    // 高度300px 宽度自适应
    height: 300px;
    width: auto;
    // 图片居中
    display: block;
    margin: 0 auto;
  }
}
</style>

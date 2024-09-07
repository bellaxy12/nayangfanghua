<script setup>
import { ref } from 'vue'

const albumCover = ref('/src/assets/images/zhuanji2.jpg') // 替换为你的专辑封面图片路径
const isPlaying = ref(false)
// const progress = ref(0) // 进度条当前进度，假设为百分比

function togglePlay() {
  isPlaying.value = !isPlaying.value
  // 这里可以添加播放或暂停音乐的逻辑
}

function previousSong() {
  console.log('Playing previous song...')
  // 上一首歌的逻辑
}

function nextSong() {
  console.log('Playing next song...')
  // 下一首歌的逻辑
}

// 假设的更新进度条的方法（需要实际与音频播放同步）
// 这里不实现具体的同步逻辑，只是提供一个示例
// function updateProgress(percent) {
//   progress.value = percent
// }

// 注意：在<script setup>中，不需要return任何内容
// 所有顶层绑定的变量和函数都会自动暴露给模板
</script>
<template>
  <div class="music-player-card">
    <img :src="albumCover" alt="Album Cover" class="album-cover" />
    <div class="music-info">
      <h3>如果没有你</h3>
    </div>
    <div class="controls">
      <input type="range" class="progress-bar" />
      <div class="buttons">
        <svg @click="previousSong" class="icon" aria-hidden="true">
          <use xlink:href="#icon-shangyishou"></use>
        </svg>
        <svg @click="togglePlay" class="icon toggle" aria-hidden="true" v-if="isPlaying">
          <use xlink:href="#icon-bofang"></use>
        </svg>
        <svg @click="togglePlay" class="icon toggle" aria-hidden="true" v-else>
          <use xlink:href="#icon-zanting"></use>
        </svg>
        <svg @click="nextSong" class="icon" aria-hidden="true">
          <use xlink:href="#icon-xiayishou"></use>
        </svg>
      </div>
    </div>
  </div>
</template>

<style scoped>
.buttons {
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  margin-top: 10px;
  .icon {
    width: 30px;
    height: 30px;
  }
  .icon:hover {
    cursor: pointer;
  }
  .toggle {
    width: 40px;
    height: 40px;
  }
}
input.progress-bar[type='range'] {
  -webkit-appearance: none; /* 去除默认的样式 */
  width: 220px; /* 根据需要设置宽度 */
  height: 5px; /* 轨道的高度 */
  background-color: pink; /* 背景颜色设置为粉色 */
  outline: none; /* 去除焦点时的轮廓 */
  opacity: 0.7; /* 可选：设置透明度 */
  -webkit-transition: 0.2s; /* 平滑过渡效果 */
  transition: opacity 0.2s;
}

input.progress-bar[type='range']::-webkit-slider-thumb {
  -webkit-appearance: none; /* 去除默认的滑块样式 */
  appearance: none; /* 对于非Webkit浏览器 */
  width: 10px; /* 滑块的宽度 */
  height: 10px; /* 滑块的高度 */
  background: #fc8ab7; /* 滑块颜色设置为蓝色 */
  cursor: pointer; /* 鼠标悬停时显示指针形状 */
  border-radius: 50%; /* 滑块形状设置为圆形 */
}
.music-player-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 10px;
}
.album-cover {
  width: 200px; /* 或其他合适的尺寸 */
  border-radius: 10px;
  margin-bottom: 10px;
}

.controls {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}

.progress-bar {
  width: 220px;
  background-color: #fecade;
  height: 5px;
  border-radius: 5px;
}

.is-playing {
  color: red; /* 播放按钮激活时的颜色 */
}
</style>

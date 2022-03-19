<script setup>
import { reactive } from "@vue/reactivity"

const mediaInfo = reactive({
  data: [
    {
      pic: "https://picsum.photos/360/216",
      date: "2021-12-22",
      cate: "經濟日報",
      content: "成功大學勇奪國家新創八獎項"
    },
    {
      pic: "https://picsum.photos/360/216",
      date: "2021-12-11",
      cate: "Panasonic 企業社會責任網",
      content: "2020年 綠色生活創意設計競賽成果"
    },
    {
      pic: "https://picsum.photos/360/216",
      date: "2021-06-10",
      cate: "CHEERS 快樂工作人",
      content: "創新商機，智聯網創業好點子價值百萬！"
    },
    {
      pic: "https://picsum.photos/360/216",
      date: "2021-12-11",
      cate: "Panasonic 企業社會責任網",
      content: "2020年 綠色生活創意設計競賽成果"
    },
    {
      pic: "https://picsum.photos/360/216",
      date: "2021-06-10",
      cate: "CHEERS 快樂工作人",
      content: "創新商機，智聯網創業好點子價值百萬！"
    },
  ]
})
</script>

<template>
  <div class="media-area">
    <div class="container">
      <div class="nav">
        <div class="title-area">
          <h2 class="title">Media</h2>
          <h3 class="subtitle">媒體報導</h3>
        </div>
        <div class="arrow-group">
          <button class="arrow left"></button>
          <button class="arrow right"></button>
        </div>
      </div>

      <div class="row">
        <div v-for="(media, idx) in mediaInfo.data" :key="idx" class="media-item">
          <div class="pic">
            <img :src="media.pic" :alt="media.content" />
          </div>
          <div class="date">
            <span>{{ media.content }}</span>
          </div>
          <div class="txt">
            <div class="cate">[{{ media.cate }}]</div>
            <div class="content">{{ media.content }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.media-area {
  padding-top: 100px;
}
.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  .arrow-group {
    display: flex;
    & > button {
      border: 1px solid #A5A5A5;
      width: 70px;
      height: 70px;
      background: #fff;
      & + button {
        border-left: none;
      }
    }
    .txt {
      padding-top: 15px;
      .date {
        padding-bottom: 15px;
      }
    }
  }
}
.row {
  display: grid;
  grid-template-columns: repeat(3, 1fr) 20%;
  gap: 25px;
  width: 100%;
  overflow: hidden;
  .media-item {
    img {
      width: 100%;

    }
  }
}
</style>
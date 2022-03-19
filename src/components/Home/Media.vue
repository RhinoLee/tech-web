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
    </div>

    <div class="container slider">
      <div class="row">
        <div class="slider-row">
          <div v-for="(media, idx) in mediaInfo.data" :key="idx" class="media-item">
            <div class="pic">
              <img :src="media.pic" :alt="media.content" />
            </div>
            <div class="txt">
              <div class="date">
                <span>{{ media.date }}</span>
              </div>
              <div class="cate">[{{ media.cate }}]</div>
              <div class="content">{{ media.content }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.media-area {
  padding-top: 100px;
  .container {
    &.slider {
      max-width: none;
      width: 100%;
      .row {
        display: flex;
        overflow: hidden;
        width: 93%;
        margin-left: auto;
      }
    }
  }
}

.slider-row {
  display: flex;
  margin-left: -12px;
  .media-item {
    width: 33.333333%;
    padding-left: 12px;
    padding-right: 12px;
    img {
      width: 100%;
    }
    &:nth-child(5) {
      display: none;
    }
    .txt {
      padding-top: 15px;
      .cate {
        padding-bottom: 5px;
        font-weight: bold;
        font-size: 1.3rem;
      }
      .date {
        padding-bottom: 15px;
        span {
          color: $blue;
          font-weight: bold;
          font-size: 1.4rem;
        }
      }
      .content {
        font-size: 1.2rem;
      }
    }
  }
}

.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 40px;
  .arrow-group {
    display: flex;
    & > button {
      border: 1px solid #a5a5a5;
      width: 70px;
      height: 70px;
      background: #fff;
      & + button {
        border-left: none;
      }
    }
  }
}
</style>
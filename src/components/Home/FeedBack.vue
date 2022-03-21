<script setup>
import { reactive } from "@vue/reactivity"
const feedBackInfo = reactive({
  data: [
    {
      pic: "https://picsum.photos/120/120",
      cate: "居家復健",
      title: "成大復健科醫師",
      years: 43,
      content: "疫情下的好幫手，我都推薦給病患在家使用，在家也輕鬆復健。"
    },
    {
      pic: "https://picsum.photos/120/120",
      cate: "居家復健",
      title: "成大復健科醫師",
      years: 43,
      content: "疫情下的好幫手，我都推薦給病患在家使用，在家也輕鬆復健。"
    },
    {
      pic: "https://picsum.photos/120/120",
      cate: "居家復健",
      title: "成大復健科醫師",
      years: 43,
      content: "疫情下的好幫手，我都推薦給病患在家使用，在家也輕鬆復健。"
    },
    {
      pic: "https://picsum.photos/120/120",
      cate: "居家復健",
      title: "成大復健科醫師",
      years: 43,
      content: "疫情下的好幫手，我都推薦給病患在家使用，在家也輕鬆復健。"
    },
  ]
})
</script>

<template>
  <div class="feedback-area">
    <div class="container">
      <div class="title-area">
        <h2 class="title">Feedback</h2>
        <h3 class="subtitle">使用者好評回饋</h3>
        <h4 class="intro">使用者回饋好評使用者回饋好評使用者回饋好評使用者回饋好評使用者回饋好評使用者回饋好評使用。</h4>
      </div>
      <div class="feedback-box">
        <div class="item" v-for="(feedBack, idx) in feedBackInfo.data" :key="idx">
          <div class="pic">
            <img :src="feedBack.pic" :alt="feedBack.content" />
          </div>
          <div class="txt">
            <div class="content">{{ feedBack.content }}</div>
            <div class="chac">{{ feedBack.years }}歲 / {{ feedBack.title }}</div>
            <div class="cate">{{ feedBack.cate }}</div>
          </div>
        </div>
      </div>

      <div class="button-wrap">
        <a href="javasacipt:;">View More</a>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
img {
  width: 100%;
}
.feedback-area {
  padding-top: 190px;
  padding-bottom: 100px;
  h4.intro {
    margin-top: 40px;
    padding-bottom: 32px;
    font-size: 1.1rem;
    font-weight: bold;
  }
  .title-area {
    padding-bottom: 32px;
    text-align: center;
  }
  .feedback-box {
    display: grid;
    grid-template-columns: 1fr 1fr;
    .item {
      display: grid;
      grid-template-columns: 16% 23% 1fr;
      margin-bottom: 35px;
      padding-right: 57px;
      * {
        letter-spacing: 1px;
      }
      &:nth-child(2n+1) {
        border-right: 1px solid #CCC;
      }
      .pic {
        grid-column: 2 / 3;
      }
      .txt {
        grid-column: 3 / 4;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding-left: 16px;
      }
      .content {
        font-size: 1.3rem;
        line-height: 1.7;
      }
      .chac {
        font-weight: bold;
        font-size: 1.3rem;
        line-height: 1.6;
      }
      .cate {
        font-size: 1.1rem;
        font-weight: bold;
        background: $blue;
        color: #fff;
        width: 88px;
        padding: 5px 7px;
        text-align: center;
        border-radius: 5px;
      }
    }
  }
  .button-wrap {
    text-align: center;
    margin-top: 96px;
  }
}
</style>
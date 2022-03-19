<script setup>
import { reactive } from "@vue/reactivity";
const newsData = reactive({
  newsList: [
    {
      id: 1,
      cate: "最新消息",
      date: "2022-02-10",
      title: "立人里臨床收案結束！",
      link: "javascript:;"
    },
    {
      id: 2,
      cate: "最新消息",
      date: "2022-02-11",
      title: "立人里臨床收案結束！01",
      link: "javascript:;"
    },
    {
      id: 3,
      cate: "最新消息",
      date: "2022-02-12",
      title: "立人里臨床收案結束！02",
      link: "javascript:;"
    },
  ]
})

</script>

<template>
  <div class="wrapper">
    <div class="news-area">
      <div class="container">
        <ul>
          <li v-for="news in newsData.newsList" :key="news.id">
            <div class="cate">{{ news.cate }}</div>
            <div class="date-title">
              <span class="date">{{ news.date }}</span>
              <h3 class="title">{{ news.title }}</h3>
            </div>
            <div class="link">
              <div class="button-wrap">
                <a :href="news.link">View More</a>
              </div>
            </div>
          </li>
        </ul>
      </div>
    </div>
    <div class="about-area">
      <div class="about-box one">
        <div class="container">
          <div class="pic">
            <img class="full-width" src="https://picsum.photos/626/551" alt />
          </div>
          <div class="txt">
            <h3 class="subtitle">AIFREE | 關於我們</h3>
            <h2 class="title">提供您最適化的醫療服務</h2>
            <p>人工智慧的發展、大數據、物聯網等資通訊技術的導入，整合醫療與資通訊科技跨域整合，以創新的資料分析融合醫學領域專業知識，提升醫療服務效率與品質。</p>
            <div class="button-wrap">
              <a href="javascript:;">View More</a>
            </div>
          </div>
        </div>
      </div>
      <div class="about-box two">
        <div class="container">
          <div class="pic">
            <img src="https://picsum.photos/1050/590" alt />
            <div class="txt">
              <div class="title-area">
                <h2 class="title">智慧醫療</h2>
                <div class="circle"></div>
              </div>
              <p>姓啦國族樁到強中戰謝音相外肯戰謝音相外肯污，音外肯我霍針自在大記制，要人不法蝕很我。</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
img {
  width: 100%;
}
h3.subtitle {
  padding-bottom: 10px;
}
.news-area {
  padding-top: 100px;
  ul {
    margin: 0 auto;
    width: 100%;
    max-width: 1000px;
    li {
      display: grid;
      grid-template-columns: 7% 14% 1fr 129px 3%;
      background: $blue-gradient-news;
      padding: 10px 0;
      border-radius: 100px;
      * {
        color: #fff;
        letter-spacing: 1px;
      }
      & + li {
        margin-top: 15px;
      }
      .cate {
        grid-column: 2 / 3;
        font-weight: bold;
      }
      .date-title {
        grid-column: 3 / 4;
        display: flex;
        align-items: center;
        h3.title {
          padding-left: 10px;
          font-weight: bold;
        }
      }
      .link {
        grid-column: -3 / -2;
      }
    }
  }
}
.about-area {
  // 47%
  padding-top: 103px;
  padding-bottom: 60px;
  .about-box {
    &.one {
      .container {
        display: grid;
        grid-template-columns: 53% 47%;
        margin: 0 auto;
        width: 100%;
        max-width: 1000px;
        .pic {
          grid-column: 1 / 2;
          max-width: 626px;
        }
        .txt {
          grid-column: 2 / 3;
          padding-left: 92px;
          padding-top: 63px;
        }
        .button-wrap {
          padding-top: 20px;
        }
      }
    }
    &.two {
      padding-top: 118px;
      .container {
        .pic {
          position: relative;
          border-radius: 33px 33px 33px 0px;
          overflow: hidden;
          .txt {
            position: absolute;
            left: 0;
            bottom: 0;
            padding-top: 40px;
            padding-bottom: 30px;
            padding-left: 46px;
            padding-right: 54px;
            width: 46%;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 0 25px 0 0;
          }
        }
        .title-area {
          display: flex;
          align-items: center;
          justify-content: space-between;
          .circle {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: #64B6C8CC;
          }
        }
      }
    }
  }
}
</style>
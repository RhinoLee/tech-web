<script setup>
import { defineProps } from "vue";
const props = defineProps({
  navList: {
    type: Array,
    default: () => ([])
  }
})
const nowYears = new Date().getFullYear()

</script>
<template>
  <footer>
    <div class="container">
      <div class="footer-container">
        <div class="logo">
          <div class="pic">
            <img src="https://picsum.photos/159/39" alt="智遊科技" />
          </div>
          <div class="info">
            <ul>
              <li>智遊科技股份有限公司</li>
              <li>(06)2757575 #54336</li>
              <li>701台南市東區大學路一段</li>
            </ul>
          </div>
        </div>
        <div class="nav">
          <ul class="main-ul">
            <li v-for="(navItem, idx) in props.navList" :key="idx">
              <div v-if="navItem.title !== '聯絡我們'">
                <span>{{ navItem.title }}</span>
              </div>
              <ul class="second-ul" v-if="navItem.subNavList.length > 0">
                <li v-for="(subNavItem, idx) in navItem.subNavList" :key="idx">
                  <a :href="subNavItem">{{ subNavItem.title }}</a>
                </li>
              </ul>
            </li>
          </ul>
        </div>
        <div class="contact">
          <div class="button-wrap">
            <a href="#">CONTACT US</a>
          </div>
        </div>
      </div>
    </div>

    <div class="copyright-container">
      <div class="copyright">&copy;{{ nowYears }} AIFREE All rights reserved.</div>
      <ul>
        <li>
          <a href="#">隱私權政策</a>
        </li>
        <li>
          <a href="#">使用條款</a>
        </li>
        <li>
          <a href="#">銷售與退款</a>
        </li>
        <li>
          <a href="#">網站地圖</a>
        </li>
      </ul>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.footer-container {
  padding-bottom: 32px;
  @media (max-width: 575px) {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  @media (min-width: 576px) {
    display: grid;
    grid-template-columns: 15% 30px 1fr 30px 15%;
  }
  @media (min-width: 1200px) {
    display: grid;
    grid-template-columns: 15% 9% 55% 6% 15%;
  }
  .logo {
    img {
      width: 100%;
    }
    @media (max-width: 1199px) {
      margin-bottom: 30px;
    }
    @media (min-width: 576px) {
      grid-column: 1 / 2;
    }
    .info {
      li {
        margin-top: 10px;
        @media (max-width: 575px) {
          text-align: center;
        }
      }
    }
  }
  .nav {
    li {
      @media (max-width: 575px) {
        // text-align: center;
      }
    }
    @media (min-width: 576px) {
      grid-column: 3 / 4;
    }
    .main-ul {
      display: grid;
      grid-template-columns: repeat(2, auto);
      gap: 40px 25px;
      @media (min-width: 576px) {
        grid-template-columns: repeat(3, auto);
        gap: 25px;
      }
      @media (min-width: 768px) {
        grid-template-columns: repeat(4, auto);
      }
      @media (min-width: 1400px) {
        grid-template-columns: repeat(5, auto);
        gap: 50px;
      }
      li {
        div {
          padding-bottom: 20px;
          font-size: 1.1rem;
          letter-spacing: 1px;
        }
      }
    }
    .second-ul {
      li {
        a {
          position: relative;
          display: inline-block;
          border-bottom: 1px solid $gray;
          padding-left: 10px;
          font-size: 1rem;
          &::after {
            content: "";
            display: block;
            position: absolute;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 5px;
            height: 1px;
            background: $gray;
          }
        }
        & + li {
          margin-top: 15px;
        }
      }
    }
  }
  .contact {
    @media (min-width: 576px) {
      grid-column: 5 / 6;
    }
    .button-wrap {
      border: 1px solid $dark;
      border-radius: 8px;
      margin-top: 20px;
    }
    a {
      display: block;
      padding: 8px 5px;
      font-weight: 600;
      font-size: 12px;
      letter-spacing: 1px;
      line-height: 14px;
      @media (min-width: 768px) {
        padding: 10px 20px;
      }
      @media (min-width: 1200px) {
        padding: 10px 42px;
      }
    }
  }
}
.copyright-container {
  display: flex;
  padding-bottom: 35px;
  @media (max-width: 575px) {
    flex-direction: column;
    align-items: center;
  }
  @media (min-width: 576px) {
    margin-right: 35px;
    justify-content: flex-end;
  }
  ul {
    display: flex;
    @media (max-width: 575px) {
      margin-top: 10px;
    }
    @media (min-width: 576px) {
      margin-left: 30px;
    }
    li + li {
      border-left: 1px solid $dark;
    }
    a {
      display: block;
      padding: 0 5px;
    }
  }
}
</style>
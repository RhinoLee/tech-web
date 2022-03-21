<script setup>
import { defineProps } from "vue";
const props = defineProps({
  navList: {
    type: Array,
    default: () => ([])
  }
})
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
  </footer>
</template>

<style lang="scss" scoped>
.footer-container {
  display: grid;
  grid-template-columns: 15% 9% 55% 6% 15%;
  padding-bottom: 32px;
  .logo {
    grid-column: 1 / 2;
    .info {
      li {
        margin-top: 10px;
      }
    }
  }
  .nav {
    grid-column: 3 / 4;
    .main-ul {
      display: grid;
      grid-template-columns: repeat(5, auto);
      gap: 50px;
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
    grid-column: 5 / 6;
    .button-wrap {
      border: 1px solid $dark;
      border-radius: 8px;
      margin-top: 20px;
    }
    a {
      display: block;
      padding: 10px 42px;
      font-weight: 600;
      font-size: 12px;
      letter-spacing: 1px;
      line-height: 14px;
    }
  }
}
</style>
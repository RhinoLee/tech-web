<script setup>
import { ref } from "@vue/reactivity";
import { defineProps } from "vue";
const props = defineProps({
  navList: {
    type: Array,
    default: () => ([])
  }
})
const isMenuOpen = ref(false)

function burgerHandler() {
  isMenuOpen.value = !isMenuOpen.value
}

</script>

<template>
  <header>
    <div class="header-container">
      <div @click="burgerHandler" class="burger-menu" :class="{ close: isMenuOpen }">
        <div class="burger"></div>
      </div>
      <div class="logo">
        <img src="https://picsum.photos/159/39" alt="智遊科技" />
      </div>
      <div class="nav" :class="{ open: isMenuOpen }">
        <ul class="main-ul">
          <li v-for="(navItem, idx) in props.navList" :key="idx">
            <a :href="navItem.link">
              <span>{{ navItem.title }}</span>
              <i v-if="navItem.subNavList.length > 0"></i>
            </a>
            <ul class="second-ul" v-if="navItem.subNavList.length > 0">
              <li v-for="(subNavItem, idx) in navItem.subNavList" :key="idx">
                <a :href="subNavItem">{{ subNavItem.title }}</a>
              </li>
            </ul>
          </li>
          <li class="lang">
            <select>
              <option value="tw">中文</option>
              <option value="en">English</option>
            </select>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>

<style scoped lang="scss">
a {
  color: $gray;
  text-decoration: none;
}
header {
  overflow: hidden;
}
.burger-menu {
  position: fixed;
  top: 5.5%;
  right: 40px;
  width: 30px;
  height: 25px;
  cursor: pointer;
  z-index: 2;
  @media (min-width: 576px) {
    display: none;
  }
  .burger {
    position: relative;
    width: 100%;
    height: 5px;
    background: $blue-gradient-news;
    border-radius: 5px;
    transition: 0.3s linear all;
    &::after,
    &::before {
      content: "";
      position: absolute;
      display: block;
      width: 100%;
      height: 100%;
      background: $blue-gradient-news;
      border-radius: 5px;
      transition: 0.3s linear all;
    }
    &::after {
      bottom: -10px;
    }
    &::before {
      top: -10px;
    }
  }
  &.close {
    .burger {
      transform: rotate(45deg);
      &::after {
        transform: rotate(90deg);
        bottom: 0;
      }
      &::before {
        transform: rotate(90deg);
        top: 0;
      }
    }
  }
}
.header-container {
  padding: 24px 0;
  height: 88px;
  @media (min-width: 576px) {
    display: grid;
    grid-template-columns: 30px 1fr 2fr 30px;
  }
  @media (min-width: 768px) {
    display: grid;
    grid-template-columns: 40px 1fr 2fr 77px;
  }

  .logo {
    @media (min-width: 576px) {
      grid-column: 2 / 3;
    }
  }
  .nav {
    width: 100%;
    height: 100%;
    z-index: 1;
    @media (max-width: 575px) {
      position: fixed;
      top: 0;
      left: -100%;
      padding-top: 88px;
      padding-left: 30px;
      overflow-y: scroll;
      background: $blue-gradient;
      transition: 0.3s linear all;
    }
    @media (min-width: 576px) {
      grid-column: -3 / -2;
    }
    &.open {
      @media (max-width: 575px) {
        left: 0;
      }
    }
    ul {
      height: 100%;
      @media (min-width: 576px) {
        display: grid;
        grid-template-columns: repeat(7, 1fr);
      }
      li {
        // padding: 0 10px;
        @media (min-width: 576px) {
          align-self: center;
          text-align: center;
          
        }
      }
      a {
        display: block;
        width: 100%;
        padding: 5px 0;
        @media (max-width: 575px) {
          color: #fff;
        }
        span {
          font-size: 1.1rem;
        }
      }
    }
    .main-ul {
      @media (max-width: 575px) {
        width: 80%;
      }
      > li:not(.lang) {
        @media (max-width: 575px) {
          border-bottom: 1px solid #fff;
          & + li {
            margin-top: 10px;
          }
        }
        a {
          @media (max-width: 575px) {
            display: flex;
            justify-content: space-between;
          }
          span {
            @media (max-width: 575px) {
              color: #fff;
            }
          }
          i {
            position: relative;
            width: 10px;
            &::before,
            &::after {
              content: "";
              display: block;
              position: absolute;
              width: 100%;
              height: 1px;
              background: #fff;
            }
            &::after {
              bottom: 5px;
              left: calc(50% - 3px);
              transform: rotate(-45deg);
            }
            &::before {
              bottom: 5px;
              right: calc(50%);
              transform: rotate(45deg);
            }
          }
        }
      }
      .lang {
        select {
          width: 53px;
          border: none;
          outline: none;
          font-size: 1.1rem;
        }
      }
    }
    .second-ul {
      display: none;
    }
  }
}
</style>
<script setup>
import { defineProps } from "vue"
const props = defineProps({
  direction: {
    type: String,
    default: "left"
  },
  bannerItems: {
    type: Array,
    default: () => ({})
  }
})
</script>

<template>
  <div class="banner home">
    <div class="banner-box" v-for="(item, idx) in props.bannerItems" :key="idx">
      <img class="full-width" :src="item.pic" />
      <div class="text-box" :class="props.direction">
        <h2>
          {{ item.titleFirst }}
          <br />
          {{ item.titleSecond }}
        </h2>
        <div class="subtitle">{{ item.subtitle }}</div>
        <div class="button-wrap">
          <a :href="item.link">View More</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.banner-box {
  position: relative;
  .text-box {
    position: absolute;
    top: 27%;
    width: 51%;
    background: $blue-gradient;
    &.left {
      left: 0;
      padding-left: 90px;
      padding-right: 132px;
      border-top-right-radius: 1000px;
      border-bottom-right-radius: 1000px;
    }
    &.right {
      right: 0;
      padding-right: 90px;
      padding-left: 132px;
      border-top-left-radius: 1000px;
      border-bottom-left-radius: 1000px;
    }
    @media (min-width: 1501px) {
      height: 58%;
    }
    * {
      color: #fff;
    }
    h2 {
      padding-top: 30px;
      padding-bottom: 17px;
      font-size: 1.5rem;
      line-height: 1.3;
      letter-spacing: 1px;
      font-weight: 300;
      @media (min-width: 1051px) {
        font-size: 2rem;
      }
      @media (min-width: 1280px) {
        font-size: 3rem;
        padding-top: 53px;
      }
      @media (min-width: 1501px) {
        // padding-top: 0;
        padding-top: 17%;
        font-size: 3.8rem;
      }
    }
    .subtitle {
      padding-bottom: 20px;
      font-size: 1rem;
      line-height: 1.7;
      letter-spacing: 1px;
      @media (min-width: 1051px) {
        font-size: 1.2rem;
      }
      @media (min-width: 1280px) {
        // padding-bottom: 50px;
      }
      @media (min-width: 1501px) {
        font-size: 1.7rem;
      }
    }
    .button-wrap {
      padding-bottom: 35px;
    }
  }
}
</style>
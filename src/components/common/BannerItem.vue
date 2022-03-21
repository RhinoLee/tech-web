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
        <div class="txt">
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
  </div>
</template>

<style lang="scss" scoped>
.banner-box {
  position: relative;
  min-height: 180px;
  img {
    width: 100%;
    height: 100%;
    min-height: 180px;
    object-fit: cover;
    object-position: 50% 50%;
  }
  .text-box {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    padding-top: 30px;
    background: $blue-gradient;
    @media (min-width: 768px) {
      top: 50%;
      transform: translateY(-50%);
      padding-top: 30px;
      padding-bottom: 30px;
      width: 51%;
      height: 58%;
      max-width: 670px;
      max-height: 320px;
      top: 27%;
      transform: translateY(0px);
      .txt {
        position: absolute;
        top: 50%;
        left: 10%;
        transform: translateY(-50%);
      }
    }
    &.left,
    &.right {
      padding-left: 10px;
      padding-right: 10px;
      @media (min-width: 768px) {
        padding-left: 30px;
        padding-right: 30px;
      }
    }
    &.left {
      right: auto;
      left: 0;
      @media (min-width: 768px) {
        border-top-right-radius: 1000px;
        border-bottom-right-radius: 1000px;
        padding-left: 90px;
        padding-right: 132px;
      }
    }
    &.right {
      left: auto;
      right: 0;
      @media (min-width: 768px) {
        border-top-left-radius: 1000px;
        border-bottom-left-radius: 1000px;
        padding-right: 90px;
        padding-left: 132px;
      }
    }
    * {
      color: #fff;
    }
    h2 {
      padding-bottom: 10px;
      font-size: 1.2rem;
      letter-spacing: 1px;
      font-weight: 300;
      @media (min-width: 576px) {
        padding-bottom: 17px;
        font-size: 1.5rem;
        line-height: 1.3;
      }
      @media (min-width: 1280px) {
        padding-bottom: 17px;
        font-size: 1.5rem;
        line-height: 1.3;
      }
    }
    .subtitle {
      padding-bottom: 10px;
      font-size: 1rem;
      letter-spacing: 2px;
      line-height: 1.2;
      font-weight: 400;
      @media (min-width: 576px) {
        padding-bottom: 20px;
        line-height: 1.7;
      }
    }
  }
}
</style>
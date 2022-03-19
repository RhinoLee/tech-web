<script setup>
import BannerItem from "@/components/common/BannerItem.vue"
import { reactive } from "@vue/reactivity"

const bannerInfo = reactive({
  data: [
    {
      pic: "https://picsum.photos/1280/544",
      titleFirst: "AIFREE",
      titleSecond: "MAKE YOUR LIFE FREE.",
      subtitle: "自由微笑人生，創造無限價值。",
      link: "javascript:;"
    }
  ]
})
</script>

<template>
  <div class="banner home">
    <BannerItem direction="left" :bannerItems="bannerInfo.data"></BannerItem>
  </div>
</template>


<style lang="scss" scoped>
</style>
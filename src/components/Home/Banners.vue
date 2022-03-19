<script setup>
import BannerItem from "@/components/common/BannerItem.vue"
import { reactive } from "@vue/reactivity"

const bannerInfo = reactive({
  data: [
    {
      pic: "https://picsum.photos/1280/544",
      titleFirst: "Intelligent Health",
      titleSecond: "Promotion Service System",
      subtitle: "本產品提供一套新型的復健服務，使復健者能夠居家復健，專業人員能夠透過系 統遠端安排最適化的復健療程。本產品提供一套新型的復健服務，使復健者能夠居家復健，專業人員能夠透過系統遠端安排最適化的復健療程。",
      link: "javascript:;"
    },
    {
      pic: "https://picsum.photos/1280/544",
      titleFirst: "Children’s Intelligent",
      titleSecond: "Articulation Traing System",
      subtitle: "語言是兒童發展過程中重要且不可缺的一部分，它不僅是兒童的一種能 力，也是兒童學習、建立自信心的重要方式。兒童智慧構音訓練系統供有趣且 專業的構音訓練平台，提升家長參與度以及遠距語音訓練的精準度。",
      link: "javascript:;"
    },
  ]
})
</script>

<template>
  <div class="banner home">
    <BannerItem direction="right" :bannerItems="bannerInfo.data"></BannerItem>
  </div>
</template>


<style lang="scss" scoped>
</style>
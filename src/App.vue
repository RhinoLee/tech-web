<script setup>
import { RouterLink, RouterView } from "vue-router";
import { reactive } from "@vue/reactivity";
import Header from "@/components/common/Header.vue";
import Footer from "@/components/common/Footer.vue";

const navList = reactive({
  data: [
    {
      title: "關於我們",
      link: "#",
      subNavList: [
        {
          title: "企業故事",
          link: "#",
        },
        {
          title: "組織架構",
          link: "#",
        },
        {
          title: "團隊佳績",
          link: "#",
        },
        {
          title: "品質政策",
          link: "#",
        },
      ]
    },
    {
      title: "服務系統",
      link: "#",
      subNavList: [
        {
          title: "智慧健促服務系統",
          link: "#",
        },
        {
          title: "兒童構音服務系統",
          link: "#",
        }
      ]
    },
    {
      title: "最新消息",
      link: "#",
      subNavList: [
        {
          title: "即時快訊",
          link: "#",
        },
        {
          title: "媒體報導",
          link: "#",
        },
        {
          title: "使用者回饋",
          link: "#",
        },
      ]
    },
    {
      title: "常見問題",
      link: "#",
      subNavList: []
    },
    {
      title: "合作通路",
      link: "#",
      subNavList: []
    },
    {
      title: "聯絡我們",
      link: "#",
      subNavList: []
    },
  ]
})
</script>

<template>
  <Header :navList="navList.data"></Header>
  <RouterView />
  <Footer :navList="navList.data"></Footer>
</template>

<style>
</style>

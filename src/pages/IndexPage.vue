<template>
  <div id="indexPage">
    <h1>🐟 鱼了个鱼</h1>
    <div style="margin-bottom: 16px">修改版“羊了个羊”，仅供消遣 不适合商用！</div>
    <a-button
      block
      style="margin-bottom: 16px"
      @click="toGamePage(easyGameConfig)"
    >
      简单模式
    </a-button>
    <a-button
      block
      style="margin-bottom: 16px"
      @click="toGamePage(middleGameConfig)"
    >
      中等模式
    </a-button>
    <a-button
      block
      style="margin-bottom: 16px"
      @click="toGamePage(hardGameConfig)"
    >
      困难模式
    </a-button>
    <a-button
      block
      style="margin-bottom: 16px"
      @click="toGamePage(lunaticGameConfig)"
    >
      地狱模式
    </a-button>
    <a-button
      block
      style="margin-bottom: 16px"
      @click="toGamePage(skyGameConfig)"
    >
      天域模式
    </a-button>
    <a-button
      block
      style="margin-bottom: 16px"
      @click="toGamePage(yangGameConfig)"
    >
      羊了个羊模式
    </a-button>
    <a-button block style="margin-bottom: 16px" @click="() => toGamePage()">
      自定义 🔥
    </a-button>
    <my-ad />
    <div class="footer">
      鱼了个鱼 ©2023 
      <a href="https://blog.csdn.net/m0_68539124" target="_blank" style="color: #fff">
        克隆窝 版权所有
      </a>
      |
      <a

<script setup lang="ts">
import { useRouter } from "vue-router";
import {
  easyGameConfig,
  middleGameConfig,
  hardGameConfig,
  lunaticGameConfig,
  skyGameConfig,
  yangGameConfig,
} from "../core/gameConfig";
import { useGlobalStore } from "../core/globalStore";
import MyAd from "../components/MyAd.vue";

const router = useRouter();

const { setGameConfig } = useGlobalStore();

const toGamePage = (config?: GameConfigType) => {
  if (config) {
    setGameConfig(config);
    router.push("/game");
  } else {
    router.push("/config");
  }
};
</script>

<style scoped>
#indexPage {
  text-align: center;
}

.footer {
  background: rgba(0, 0, 0, 0.6);
  color: #fff;
  padding: 12px;
  text-align: center;
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
}
</style>

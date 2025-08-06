<script setup>
import Card from "./components/Card.vue";
import IcomButton from "./components/IcomButton.vue";
import {saveAs} from "file-saver"
import configData from "./config.json";

async function download(filename) {
  try {
    const response = await fetch(filename)
    const blob = await response.blob()
    saveAs(blob, filename)
  } catch (error) {
    console.error('下载失败:', error)
  }
}

</script>

<template>
  <div class="h-screen relative">
    <div class="absolute inset-0">
      <img :src=configData.bg_path alt=""  class="w-full h-full object-cover" />
    </div>
    <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-white/0">
    </div>
    <div class="absolute inset-x-0 bottom-10">
      <div class=" container mx-auto h-full flex flex-col xl:flex-row space-y-5 justify-between items-center">
        <Card icon="bi bi-controller" title="游戏客户端" subtitle="最新版御龙华夏游戏客户端，体验畅快游戏" :bottom=configData.game_version>
          <IcomButton icon="bi bi-download" text="Windows 版下载"></IcomButton>
        </Card>
        <Card icon="bi bi-wrench" title="辅助工具" subtitle="官方认证辅助工具，安全可靠" :bottom=configData.tool_version>
          <IcomButton icon="bi bi-download" text="游戏助手下载" @click="()=> {
      download(configData.tool_path)
    }"></IcomButton>
        </Card>
        <Card icon="bi bi-chat" title="客服中心">
          <div class="flex flex-col  justify-center items-center space-y-2">
            <div class="border-2 rounded w-32 h-32 bg-gray-400 flex items-center justify-center">
              <img :src=configData.customer_qr alt=""  class="w-full h-full object-cover" />
            </div>
            <button class="text-white">客服微信：{{configData.customer_wechat}}</button>
            <button class="text-white">客服QQ：{{configData.customer_qq}}</button>
          </div>
        </Card>
      </div>

    </div></div>
</template>

<style scoped>
</style>

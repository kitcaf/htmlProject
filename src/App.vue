<script setup lang="ts">
import { onMounted, ref } from "vue"
import { settingsStore } from "@/stores"
import { navigation } from "@/router"
import titMod from "@/components/titMod.vue"

const settings = settingsStore()
const isEmulated = ref(false)
const showTitMod = ref(false)

onMounted(() => {
  // 检查是否在设备仿真模式下
  if (window.matchMedia("(display-mode: standalone)").matches || window.navigator.userAgent.includes("Mobile")) {
    isEmulated.value = false
  } else {
    isEmulated.value = true
    showTitMod.value = true  // 在非仿真模式下显示对话框
  }

  if (settings.firstCome) {
    settings.setFirstCome(false)
    navigation("guide")
  }

  if (settings.theme === "dark") { //当前是dark模式
    document.documentElement.classList.add('dark')
  } else {
    document.documentElement.classList.remove('dark')
  }
})
</script>

<template>
  <div class="app">
    <div :class="{ 'emulated': isEmulated }">
      <router-view></router-view>
    </div>
    <titMod v-model:open="showTitMod"></titMod>
  </div>
</template>

<style lang="scss">
.app {
  height: 100vh;
  width: 100vw;
  position: relative;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}

.emulated {
  // 如果需要在仿真模式下添加样式，可以在这里定义
  width: 412px;
  height: 915px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.slide-up-enter-active,
.slide-up-leave-active {
  transition: all 0.3s ease-out;
}

.slide-up-enter-from {
  opacity: 0;
  transform: translateY(100vh);
}

.slide-up-leave-to {
  opacity: 0;
  transform: translateY(200vh);
}
</style>

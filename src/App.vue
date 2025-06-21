<template>
  <div id="app">
    <BasicLayout />
  </div>
</template>

<style>
#app {
}
</style>
<script setup lang="ts">
import BasicLayout from "@/layouts/BasicLayout.vue";
import { onMounted } from "vue";

/**
 * 全局初始化函数，有全局单次调用的代码都写在这里
 */
const doInit = () => {
  console.log("Hello, 欢迎来到 YTU Online Judge！");
};

onMounted(() => {
  doInit();
});
</script>

<template>
  <div id="globalHeader">
    <a-menu
      mode="horizontal"
      :selected-keys="selectedKeys"
      @menu-item-click="doMenuClick"
    >
      <a-menu-item
        key="0"
        :style="{ padding: 0, marginRight: '38px' }"
        disabled
      >
        <div class="title-bar">
          <img class="logo" src="../assets/oj-logo.png" alt="YTU-OJ" />
        </div>
      </a-menu-item>
      <a-menu-item v-for="item in routes" :key="item.path">
        {{ item.name }}
      </a-menu-item>
    </a-menu>
  </div>
</template>

<script setup lang="ts">
import { routes } from "@/router/routes";
import { useRouter } from "vue-router";
import { ref } from "vue";

const router = useRouter();

// 默认主页
const selectedKeys = ref(["/"]);

// 路由跳转后，更新选中的菜单项
router.afterEach((to, from, failure) => {
  selectedKeys.value = [to.path];
});

const doMenuClick = (key: string) => {
  router.push({
    path: key,
  });
};
</script>

<style scoped>
.title-bar {
  display: flex;
  align-items: center;
}

.logo {
  width: 80px;
}
</style>

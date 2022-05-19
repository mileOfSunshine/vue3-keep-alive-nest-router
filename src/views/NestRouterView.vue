<template>
  <div>
    <fieldset v-if="showBackBtn">
      <button @click="goBack">返回</button>
    </fieldset>
    <router-view v-slot="{ Component }">
      <keep-alive :include="caches">
        <component :is="Component" />
      </keep-alive>
    </router-view>
  </div>
</template>
<script>
import { routes } from "@/router";
import { findRouterWith, getCachesByRoutes } from "@/utils";

export default {
  name: "NestRouterView",
  props: {
    showBackBtn: {
      type: Boolean,
      default: true,
    },
  },
  setup() {
    // 找到所有以 NestRouterView 组件作为路由嵌套的页面
    const target = findRouterWith("NestRouterView")(routes);
    const caches = getCachesByRoutes(target);
    const goBack = () => window.history.back();

    return {
      caches,
      goBack,
    };
  },
};
</script>
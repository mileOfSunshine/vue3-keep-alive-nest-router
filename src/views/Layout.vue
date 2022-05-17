<template>
  <div>
    <header style="margin-bottom: 10px">
      <fieldset>
        <legend>导航</legend>
        <ul>
          <li><router-link to="/">首页</router-link></li>
          <li><router-link to="/about">关于</router-link></li>
          <li>
            主题
            <ul>
              <li><router-link to="/theme/1">主题1</router-link></li>
              <li>
                主题2
                <ul>
                  <li><router-link to="/theme/2/1">主题2-1</router-link></li>
                </ul>
              </li>
              <li><router-link to="/theme/3">主题3</router-link></li>
            </ul>
          </li>
        </ul>
      </fieldset>
    </header>
    <main>
      <router-view v-slot="{ Component }">
        <transition mode="out-in" name="fade-transform">
          <keep-alive :include="caches">
            <component :is="Component" />
          </keep-alive>
        </transition>
      </router-view>
    </main>
    <footer style="margin-top: 100px">Posted by: mileOfSunshine</footer>
  </div>
</template>

<script>
import { routes } from "@/router";
import { findRouterWith, getCachesByRoutes } from "@/utils";

export default {
  name: "Layout",
  setup() {
    // 找到所有以 NestRouterView 组件作为路由嵌套的页面
    const target = findRouterWith("Layout")(routes);
    const caches = getCachesByRoutes(target);
    console.log(caches, "caches==");
    return {
      caches,
    };
  },
};
</script>
<style>
a {
  margin-right: 20px;
}
</style>
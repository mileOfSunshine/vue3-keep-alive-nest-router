<template>
  <div>
    <div>关于的内容</div>
    <input v-model="remark" />
  </div>
</template>
<script>
export default {
  name: "About",
};
</script>
<script setup>
import { ref } from "vue";

const remark = ref("");
</script>
<template>
  <div>现在时间是：{{ date }}</div>
</template>
<script>
export default {
  name: "Home",
  setup() {
    return {
      date: new Date().toLocaleTimeString(),
    };
  },
};
</script>

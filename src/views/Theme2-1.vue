<template>
  <div>
    <h4>主题2-1</h4>
    【{{ date }}】
  </div>
</template>
<script>
export default {
  name: "Theme2-1",
  setup() {
    return {
      date: new Date(),
    };
  },
};
</script>

<template>
  <div>
    <h4>主题1</h4>
    【{{ date }}】
  </div>
</template>
<script>
export default {
  name: "Theme1",
  setup() {
    return {
      date: new Date(),
    };
  },
};
</script>


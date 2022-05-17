<template>
  <div>
    <h4>主题3</h4>
    【{{ date }}】
  </div>
</template>
<script>
export default {
  name: "Theme3",
  setup() {
    return {
      date: new Date(),
    };
  },
};
</script>
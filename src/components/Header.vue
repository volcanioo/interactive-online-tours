<template>
  <div class="header">
    <div>
      <img src="@/assets/images/homeday-logo.svg" alt="Homeday">
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
};
</script>
<style lang="scss" scoped>
.header {
  height: 80px;
  background: white;
  width: 100%;
  display: flex;
  img {
    max-height: 100%;
    padding: 15px;
  }
}
</style>

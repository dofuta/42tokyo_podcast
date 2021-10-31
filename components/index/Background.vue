<template>
  <div :class="'background ' + asset.area" :style="{backgroundImage: `url(${asset.path})`}"></div>
</template>

<script>
export default {
  props: [
    'asset'
  ],
}
</script>

<style lang="scss" scoped>
  .background
  {
    height: 100%;
    &.top {
      background-size: cover;
      position: absolute;
      width: 70vw;
      height: 150vh;
      right: 0;
      top: 0;
    }
    &.bottom {
      background-size: cover;
      position: absolute;
      width: 70vw;
      height: 150vh;
      left: 0;
      bottom: 0;
    }
  }
</style>

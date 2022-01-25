<template>
  <div class="about">
    <div class="item">
      <div class="item" v-for="item in items" :key="item.title">
      <p class="item__desc">{{item.desc}}</p>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  props: [
    'items'
  ],
}
</script>

<style lang="scss" scoped>
    .about {
      margin-top: 50px;
      .item {
        margin-bottom: 40px;
        &__desc {
          font-weight: $font-medium;
        }
      }
    }
</style>

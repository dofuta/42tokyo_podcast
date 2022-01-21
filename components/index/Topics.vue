<template>
  <div class="topics">
    <div class="item" v-for="item in items" :key="item.title">
      <p class="item__title" v-html="item.title"></p>
      <p class="item__desc">{{item.desc}}</p>
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
    .topics {
      margin-top: 50px;
      .item {
        margin-bottom: 40px;
        &__title {
          // border-bottom: 1px solid $black;
          line-height: 1.4rem;
          font-weight: $font-bold;
          margin-bottom: 15px;
        }
        &__desc {
          font-weight: $font-medium;
        }
      }
    }
</style>

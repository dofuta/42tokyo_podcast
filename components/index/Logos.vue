<template>
  <div class="logos">
    <div class="logos__item" v-for="item in items" :key="item.alt">
      <img :src="item.src" :alt="item.alt"/>
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
  .logos
  {
    display: flex;
    flex-wrap: wrap;
    &__item{
      padding: 10px 0;
      margin-right: 40px;
      img {
        height: 60px;
        @media (max-width: $tablet-width) {
          height: 40px;
        }
      }
    }
  }
</style>

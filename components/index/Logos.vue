<template>
  <div class="logos">
    <a class="logos__item" v-for="item in items" :key="item.alt" :href="item.url" target="_blank" rel="noreferrer noopener">
      <img :src="item.src" :alt="item.alt"/>
    </a>
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
      margin-right: 40px;
      background-color: $white;
      border-radius: 10px;
      img {
        height: 45px;
        transition: opacity 0.3s;
        border-radius: 5px;
        @media (max-width: $tablet-width) {
          height: 40px;
        }
        &:hover {
          opacity: 0.7;
        }
      }
    }
  }
</style>

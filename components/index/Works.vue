<template>
  <div class="works">
    <div class="item" v-for="item in items" :key="item.title">
      <img :src="item.img.src" :alt="item.img.alt"/>
      <div class="item__desc">
        <p class="title">
          {{item.title}}
        </p>
        <p class="desc">
          {{item.desc}}
        </p>
        <a class="link" :href="item.link" target='_blank' rel='noreferrer'>
          Openseaで見る >
        </a>
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
  .works
  {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    .item{
      // background-color: yellow;
      padding: 10px 0;
      display: flex;
      flex-wrap: wrap;
      img {
        border-radius: 10px;
        width: 200px;
        @media (max-width: $tablet-width) {
          max-width: 50%;
        }
      }
      &__desc {
        padding: 25px;
        line-height: 3rem;
        width: 300px;
        @media (max-width: $tablet-width) {
          max-width: 50%;
          line-height: 2rem;
          font-size: 0.8rem;
        }
        .title {
          font-weight: $font-medium;
        }
        .desc {
          font-weight: $font-medium;
        }
        .link {
          font-weight: $font-medium;
        }
      }
    }
  }
</style>

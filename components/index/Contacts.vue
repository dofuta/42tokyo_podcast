<template>
  <div class="contacts">
    <a class="contacts__item" v-for="item in items" :key="item.alt" :href="item.link" target="_blank" rel='noreferrer' :style="{borderColor: item.color, backgroundColor: item.color}">
      <div class="wrapper">
        <span :style="{ color: item.color }">{{item.text}}</span>
        <img :src="item.img.src" :style="{width: item.img.w + 'px', height: item.img.h + 'px'}"/>
      </div>
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
  .contacts
  {
    display: flex;
    flex-wrap: wrap;
    &__item{
      text-decoration: none;
      border: 2px solid $black;
      line-height: 40px;
      border-radius: 40px;
      margin-right: 40px;
      margin-bottom: 20px;
      @media (max-width: $tablet-width) {
        margin: 0 auto;
        margin-bottom: 20px;
      }
      .wrapper {
        border-radius: 40px;
        width: 100%;
        height: 100%;
        padding: 10px 40px;
        background-color: rgba(255,255,255,1);
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        span {
          display: inline-block;
          vertical-align: middle;
          font-weight: $font-bold;
          color: rgba(0,169,244, 1);
          transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        img {
          display: inline-block;
          vertical-align: middle;
        }
        &:hover {
          background-color: rgba(255,255,255,0);
          transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
          span {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            color: rgba(255, 255, 255, 1) !important;
          }
        }
      }
    }
  }
</style>

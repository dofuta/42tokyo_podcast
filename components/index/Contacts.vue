<template>
  <div class="contacts">
    <a class="contacts__item" v-for="item in items" :key="item.alt" :href="smartphone ? item.link_sp : item.link_pc" target="_blank" rel='noreferrer' :style="{borderColor: item.color, backgroundColor: item.color}">
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
  data: function () {
    return {
      width: window.innerWidth,
      height: window.innerHeight,
      smartphone: false,
    }
  },
  methods: {
    handleResize: function() {
      this.width = window.innerWidth;
      this.height = window.innerHeight;
      this.smartphone = this.width < 768 ? true : false;
    }
  },
  mounted: function () {
    window.addEventListener('resize', this.handleResize)
  },
  beforeDestroy: function () {
    window.removeEventListener('resize', this.handleResize)
  }
}
</script>

<style lang="scss" scoped>
  .contacts
  {
    display: flex;
    flex-wrap: wrap;
    &__item{
      text-decoration: none;
      border: 2px solid $white;
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
        background-color: $black;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        cursor: pointer;
        span {
          display: inline-block;
          vertical-align: middle;
          font-weight: $font-bold;
          color: rgba(0,169,244, 1);
          transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
          cursor: pointer;
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

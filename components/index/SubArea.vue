<template>
  <div class="subarea" :id="id">
    <div class="subarea__title poppins">
      <h2>{{ title }}</h2>
    </div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: [
    'title',
    'id',
  ],
}
</script>

<style lang="scss" scoped>
  .subarea {
    padding: 20px;
    width: 100%;
    &__title {
      margin-bottom: 30px;
      h2 {
        padding: 10px 0;
        display: inline;
        line-height: 100px;
        color: $white;
        font-size: 2.0rem;
        font-weight: $font-bold;
        position: relative;
        &:after {
          content: '';
          display: inline-block;
          position: absolute;
          top: 60px;
          left: 0;
          width: 60px;/*線の長さ*/
          height: 8px;/*線の太さ*/
          background-color: $green;/*線の色*/
        }
      }
    }
  }
</style>

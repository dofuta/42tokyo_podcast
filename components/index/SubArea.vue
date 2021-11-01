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
        border-bottom: 1px solid $black;
        padding: 30px 0;
        display: inline;
        line-height: 100px;
        color: $black;
        font-weight: $font-bold;
      }
    }
  }
</style>

<template>
  <client-only>
    <div :class="{fadeIn: visible, fadeOut: !visible}">
      <slot v-show="visible"></slot>
    </div>
  </client-only>
</template>
<script>
  export default {
    data() {
      return {
        visible: false
      };
    },
    created() {
      if (process.browser) {
        window.addEventListener("scroll", this.handleScroll);
      }
    },
    destroyed() {
      if (process.browser) {
        window.removeEventListener("scroll", this.handleScroll);
      }
    },
    methods: {
      handleScroll() {
        if (!this.visible && process.browser) {
          var top = this.$el.getBoundingClientRect().top;
          this.visible = top < window.innerHeight - 200;
        }
      }
    }
  }
</script>

<style scoped>
.fadeOut {
  opacity: 0;
}

.fadeIn
{
  animation: fadeIn 2.0s;
}
@keyframes fadeIn
{
  0%
  {
    opacity: 0;
    transform: translateY(100px);
  }
  100%
  {
    opacity: 1;
    transform: translateY(0px);
  }
}
</style>

<template>
  <header>
    <div class="header">
      <div class="header__logo">
        <NuxtLink to="/" class="link"><img src="@/assets/img/n42.logo.png"></NuxtLink>
      </div>
      <div class="header__menu">
        <NuxtLink to="/team" class="link">TEAM</NuxtLink>
        <NuxtLink to="/contact" class="link">CONTACT</NuxtLink>
      </div>

    </div>
  </header>
</template>

<style lang='scss' scoped>
.header {
  width: 100vw;
  z-index: 100;
  position: fixed;
  padding: 20px;
  display: flex;
  // background-color: $white;
  @media (max-width: $tablet-width) {
    justify-content: space-between;
  }
  &__logo {
    img {
      width: 120px;
    }
  }
  &__menu {
    margin-left: 30px;
    .link {
      font-size: 1.4em;
      font-weight: $font-middle;
      color: $black;
      line-height: 40px;
      margin: 0 10px;
    }
  }
}
</style>

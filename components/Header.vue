<template>
  <header class="header">
    <div class="header__logo">
      <NuxtLink to="/" class="link">
        <img src="@/assets/img/logo.png">
        
      </NuxtLink>
    </div>
    <div class="header__menu">
      <a href="#team" class="link">
        <span class="mask">
          <div class="link-container">
            <span class="link-title1 title">NUMBERS</span>
            <span class="link-title2 title">一覧</span>
          </div>
        </span>
      </a>
      <a href="#contact" class="link">
        <span class="mask">
          <div class="link-container">
            <span class="link-title1 title">CONTACT</span>
            <span class="link-title2 title">お問い合わせ</span>
          </div>
        </span>
      </a>
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
      width: 160px;
    }
  }
  &__menu {
    margin-left: 30px;
    display: flex;
    .link {
      text-decoration: none;
      font-size: 1.2em;
      font-weight: $font-medium-bold;
      color: $black;
      line-height: 40px;
      margin: 0 10px;
    }
  }
}





.link {
  align-items: center;
  color: #000;
  text-decoration: none;
  display: flex;
}

/* Hide extra text */
.mask {
  position: relative;
  padding: 0;
  height: 20px;

  /*  Remove overflow to see how it works　:) */
  overflow: hidden;
}

.link-container {
  transition: transform 0.4s ease;
}

.title {
  display: block;

  /*  Set same font-size and line height  */
  font-size: 1.1rem;
  line-height: 20px;

  transition: transform 0.4s ease;
}

.link-title1 {
  transform-origin: right center;
}

.link-title2 {
  transform-origin: left center;
  transform: rotate(20deg);
}




/* Hover Action*/

/* Move up two texts (20px = font-size) */
.link:hover .link-container {
  transform: translateY(-20px);
}

/* Rotate texts a little bit */
.link:hover .link-title1 {
  transform: rotate(20deg);
}

.link:hover .link-title2 {
  transform: rotate(0);
}

/* Move arrows to right */
.link:hover .icon:first-child {
  transform: translate(40px);
}

.link:hover .icon:nth-child(2) {
  transform: translate(0px);
}


</style>

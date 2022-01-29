<template>
  <div class="toparea" >
    <p class="toparea__copy">
      <img src="@/assets/img/logo_white.png">
    </p>
    <p class="toparea__exact">
      <span class='bold'>Hello World - 42 Tokyo</span> は、<br class='only_sp'/><span class='bold'>プログラミング</span>と<a href="https://42tokyo.jp" target="_blank" rel="noopener noreferrer" class='bold'>42 Tokyo</a>の<br class='only_sp'/>そこ知れぬ魅力に迫るべく、<br class='only_sp'/>
      学生の我々が<span class='bold'>勝手に始めた<br class='only_sp'/>皆さんと作る</span>ラジオ番組です。
      <br><br>

      <span class='bold'>プログラミング</span>や<a href="https://42tokyo.jp" target="_blank" rel="noopener noreferrer" class='bold'>42 Tokyo</a>に<br class='only_sp'/>興味があるみなさん、<br class='only_sp'/>現役42生の皆さんに向けて、<br class='only_sp'/>毎回ゲストをお招きし、<br class='only_sp'/><span class='bold'>プログラミングの世界</span>との出会い<br class='only_sp'/>から、<span class='bold'>これからの世界</span>の話まで、<br class='only_sp'/>ゆるりと話していきます。

    </p>
  </div>
</template>

<script>
export default {
  props: [
    'title'
  ],
  data() {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>
  .toparea {
    width: 100%;
    padding: 100px 20px 70px 20px;
    &__copy {
      font-weight: $font-bold;
      font-size: 3rem;
      @media (max-width: $tablet-width) {
        font-size: 2rem;
      }
      img {
        width: 100%;
      }
    }
    &__desc {
      margin-top: 50px;
      .item {
        margin-bottom: 40px;
        &__title {
          border-bottom: 1px solid $white;
          line-height: 1.125rem;
          font-weight: $font-bold;
          margin-bottom: 15px;
        }
        &__desc {
          font-weight: $font-medium;
        }
      }
    }
    &__exact {
      margin-top: 100px;
      font-size: 1.125rem;
      font-weight: $font-medium;
      @media (max-width: $tablet-width) {
        font-size: 1.125rem;
        line-height: 2.0rem;
      }
      a {
        color: $green;
        text-decoration: underline;
      }
    }
  }
</style>

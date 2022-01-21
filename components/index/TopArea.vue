<template>
  <div class="toparea" >
    <p class="toparea__copy">
      Hello World - 42 Tokyo
    </p>
    <p class="toparea__exact">
      <span class='bold'>Hello Wolrd - 42 Tokyo</span> は、<br class='only_sp'/><span class='bold'>プログラミング</span>と<span class='bold'>42 Tokyo</span>の<br class='only_sp'/>そこ知れぬ魅力に迫るべく、<br class='only_sp'/>
      生徒の我々が勝手に始めた<br class='only_sp'/>皆さんと作るラジオ番組です。
    </p>
    <div class="toparea__desc">
      <div class="item" v-for="item in items" :key="item.title">
        <p class="item__title" v-html="item.title"></p>
        <p class="item__desc">{{item.desc}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: [
    'title'
  ],
  data() {
    return {
      items: [
        {
          title: "THE FIRST TOUCH<br class='only_sp'/> 〜 初めてプログラミングに触れた瞬間",
          desc: 'ゲストにお呼びしたプログラマー・エンジニアが初めてプログラミングに触れた瞬間を深ぼっていく企画です。'
        },
        {
          title: '今年のベストバイ・コマンド',
          desc: '知って良かったコマンドから、便利なツールやライブラリ、アプリ、はたまた日用品まで、ゲストの「ベストバイ」を聞いていく企画です。',
        },
        {
          title: '42について',
          desc: '42 Tokyoの学生や、外部ゲストに、42について質問していきます。',
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .toparea {
    width: 100%;
    padding: 150px 20px 40px 20px;
    &__copy {
      font-weight: $font-bold;
      font-size: 3rem;
      @media (max-width: $tablet-width) {
        font-size: 2rem;
      }
    }
    &__desc {
      margin-top: 70px;
      .item {
        margin-bottom: 40px;
        &__title {
          line-height: 1.4rem;
          font-weight: $font-bold;
          margin-bottom: 15px;
        }
        &__desc {
          font-weight: $font-medium;
        }
      }
    }
    &__exact {
      margin-top: 60px;
      font-size: 1.3rem;
      font-weight: $font-medium;
      @media (max-width: $tablet-width) {
        font-size: 1.2rem;
        line-height: 2.0rem;
      }
    }
  }
</style>

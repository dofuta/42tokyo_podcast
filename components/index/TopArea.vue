<template>
  <div class="toparea" >
    <p class="toparea__copy">
      あなたの作品を<br class="only_sp"/>NFTの世界へ
    </p>
    <p class="toparea__exact">
      <span>n42</span> は、<span>NFT</span>を専門に扱う<br class="only_sp"/><span>デジタルクリエイティブチーム</span>です。<br>
      あなたの作品を、<br class="only_sp"/><span>NFTコレクション</span> として<br class="only_sp"/>世界に届けるための <br class="only_sp"/><span>技術を提供</span>しています。<br><br>

      <span>n42</span>は、よくある「技術だけ」の<br class="only_sp"/>チームではありません。<br><br>

      得意とするのは<span>課題解決</span>です。<br class="only_sp"/>時には、そのプロジェクトで<br class="only_sp"/>利用するためだけに新しい技術を<br class="only_sp"/>習得するところから始めます。<br class="only_sp"/><br class="only_sp"/>

      私たちは<span>親密なチームの一員</span>です。<br class="only_sp"/>一緒にワクワクする未来を作りましょう。
    </p>
    <div class="toparea__desc">
      <div class="item" v-for="item in items" :key="item.title">
        <p class="item__title">{{item.title}}</p>
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
          title: '1. 素材を元に様々なデジタル作品を生成',
          desc: 'NFTコレクションを構成する素材をご用意いただき、そのデータ素材を乱数によってランダム生成します。時には素材を作るところから始めます。',
        },
        {
          title: '2. 独自コントラクト・ミンティング',
          desc: '生成した画像を、1.0k ~ 10.0kのアイテム数をミンティング。独自のシステムによって、マーケットへの出品やタグづけをコンピュータで行います。ミンティングサイトの実装も行います。',
        },
        {
          title: '3. ミンティングサイト・Dappsの開発',
          desc: 'プロジェクトの需要に合わせて、既存マーケットプレイスへの出品からミンティングサイトの実装・Dapps開発まで幅広く手がけています。',
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
        margin-bottom: 20px;
        &__title {
          line-height: 4rem;
          font-weight: $font-bold;
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
      span {
        font-weight: $font-bold;
      }
    }
  }
</style>

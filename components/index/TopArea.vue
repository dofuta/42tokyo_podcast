<template>
  <div class="toparea" >
    <p class="toparea__copy">
      私たちは、<br/>
      NFTアバタープロジェクトを<br/>
      クリエイターと共創する<br/>
      技術チームです。
    </p>
    <p class="toparea__exact">
      <span>n42</span> は、<span>NFTコレクション</span><br class="only_sp"/>を専門に扱う<br class="only_sp"/>デジタルクリエイティブチームです。<br>
      あなたの <span>NFT作品</span> を、<br class="only_sp"/><span>Generative Collection</span> として<br class="only_sp"/>世界に届けるための <br class="only_sp"/><span>技術を提供</span>しています。
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
          title: '1. 画像素材を元にアバターを生成',
          desc: 'NFTコレクションを構成する素材をご用意いただき、その画像素材をレイヤーごとに重ねて、乱数によって画像をランダムに生成します。',
        },
        {
          title: '2. 自動ミンティング・自動出品',
          desc: '生成した画像を、1.0k ~ 10.0kのアイテム数をミンティング。独自のシステムによって、マーケットへの出品やタグづけをコンピュータで行います。',
        },
        {
          title: '3. 収益はETHでクリエイターの元へ',
          desc: '手数料を差し引いた全ての収益は、毎月クリエイターの元へ支払われます。税金などの計算も今後対応予定です。',
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .toparea {
    width: 100%;
    padding: 150px 20px 130px 20px;
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

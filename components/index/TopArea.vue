<template>
  <div class="toparea" >
    <p class="toparea__copy">
      NFTコレクションの<br/>
      生成から出品まで<br/>
      全てをお任せ
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
          desc: 'パーツの画像をご用意いただき、その画像を元に、大量のアバターをランダム生成します。',
        },
        {
          title: '2. 自動ミンティング・自動出品',
          desc: '1.0k ~ 10.0kのアイテム数を自動でミンティング。出品やタグづけも自動で行います。',
        },
        {
          title: '3. 収益はETHでクリエイターの元へ',
          desc: '手数料を差し引いた全ての収益は、毎月クリエイターの元へ支払われます。',
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .toparea {
    width: 100%;
    padding: 150px 20px 100px 20px;
    &__copy {
      font-weight: $font-bold;
      font-size: 3rem;
      @media (max-width: $tablet-width) {
        font-size: 2rem;
      }
    }
    &__desc {
      margin-top: 50px;
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
  }
</style>

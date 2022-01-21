<template>
  <div class="media">
    <a class="item" v-for="(item, i) in items" :key="item.title" :href="item.link" target='_blank' rel='noreferrer'>
      <img class="thumbnail" :src="item.thumbnail" alt="">
      <div class="title">
        <p>{{item.title}}
          <span v-if="i == 0">NEW!</span>
        </p>
      </div>
      <div class="date">
        <p>{{item.date}}</p>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  props: [
    'items'
  ],
}
</script>

<style lang="scss" scoped>
  .media
  {
    margin-bottom: 60px;
    .item {
      margin-top: 20px;
      border-bottom: 1px solid $black;
      border-left: 1px solid $black;
      padding: 30px;
      display: flex;
      position: relative;
      transition: opacity 0.4s ease;
      &:hover {
        opacity: 0.6;
      }
      .thumbnail {
        border-radius: 5px;
        width: 150px;
        height: 75px;
        object-fit: cover; /* この一行を追加するだけでOK! */
        @media (max-width: $tablet-width) {
          width: 100px;
          height: 50px;
        }
      }
      .title {
        font-weight: $font-bold;
        color: $black;
        display: table;               //tableタグのような表示
        width: 100%;
        height: 75px;
        padding: 0 20px;
        @media (max-width: $tablet-width) {
          height: 50px;
        }
        p {
          display: table-cell;      //tdタグのような表示
          vertical-align: middle;   //縦方向に中央寄せ
        }
        span {
          margin-left: 5px;
          border-radius: 5px;
          padding: 1px 6px;
          color: $white;
          background-color: $green;
          font-size: 0.8rem;
          font-style: italic;
        }
      }
      .date {
        position: absolute;
        color: $gray;
        bottom: 30px;
        right: 30px;
        @media (max-width: $tablet-width) {
          bottom: 10px;
        }
      }
    }
  }
</style>

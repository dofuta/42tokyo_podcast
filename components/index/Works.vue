<template>
  <div class="works">
    <div class="item" v-for="item in items" :key="item.title">
      <img :src="item.img.src" :alt="item.img.alt"/>
      <div class="item__desc">
        <p class="title">
          {{item.title}}
        </p>
        <p class="desc">
          {{item.desc}}
        </p>
        <a class="link" :href="item.link" target='_blank' rel='noreferrer'>
          <span class="mask">
            <div class="link-container">
              <span class="link-title1 title">{{item.linktitle}}で見る></span>
              <span class="link-title2 title">{{item.linktitle}}で見る></span>
            </div>
          </span>
        </a>
      </div>
    </div>
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
  .works
  {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    .item{
      // background-color: yellow;
      padding: 10px 0;
      display: flex;
      flex-wrap: wrap;
      img {
        border-radius: 10px;
        width: 200px;
        @media (max-width: $tablet-width) {
          max-width: 50%;
        }
      }
      &__desc {
        padding: 25px;
        line-height: 3rem;
        width: 300px;
        @media (max-width: $tablet-width) {
          max-width: 50%;
          line-height: 2rem;
          font-size: 0.8rem;
        }
        .title {
          // font-weight: $font-medium;
        }
        .desc {
          font-weight: $font-medium;
        }
        .link {
          font-weight: $font-medium;
        }
      }
    }
  }









  .link {
  margin-top: 10px;
  align-items: center;
  color: $blue;
  text-decoration: none;
  display: flex;
  font-weight: $font-bold;
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
  font-size: 1rem;
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

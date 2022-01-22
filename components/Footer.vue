<template>
  <client-only>
  <footer>
  <row class="footer">
    <column :xs="12" :md="6" class="leftside">
      <row class="leftside__links">
        <column :xs="6" :md="4" class="item">
          <a href="#numbers" class="link">
            <span class="mask">
              <div class="link-container">
                <span class="link-title1 title">Numbers</span>
                <span class="link-title2 title">過去放送回</span>
              </div>
            </span>
          </a>
        </column>
        <!--
        <column :xs="6" :md="4" class="item">
          <a href="#team" class="link">
            <span class="mask">
              <div class="link-container">
                <span class="link-title1 title">Members</span>
                <span class="link-title2 title">メンバー</span>
              </div>
            </span>
          </a>
        </column>
        -->
        <column :xs="6" :md="4" class="item">
          <a href="#join" class="link">
            <span class="mask">
              <div class="link-container">
                <span class="link-title1 title">Join Our Community</span>
                <span class="link-title2 title">活動を覗いてみる</span>
              </div>
            </span>
          </a>
        </column>
      </row>
      <div class="leftside__credit">
        <!-- ここにクレジットが入ります -->
      </div>
    </column>
    <column :xs="12" :md="6" class="rightside">
      <div class="rightside__info">
        <div class="logo">
          <img src="@/assets/img/hw_black.png" alt="">
        </div>
        <div class="info">
          <!-- <p>Hello World - 42 Tokyo</p> -->
          <!-- <p>メールアドレスが入ります</p> -->
        </div>
      </div>
    </column>
  </row>
  </footer>
  </client-only>
</template>

<style lang="scss" scoped>
footer {
  background-color: $black;
  .footer {
    margin: 0 auto;
    padding: 50px 20px;
    height: 300px;
    max-width: $main-width;
    color: $white;
    .leftside {
      &__links {
        .item {
          margin-bottom: 15px;
          a {
            color: $white;
            text-decoration: none;
          }
        }
      }
      &__credit {
        position: absolute;
        bottom: 0;
        left: 0;
        @media (max-width: $tablet-width) {
          display: none;
        }
        font-weight: $font-light;
        a {
          color: $white;
        }
      }
    }
    .rightside {
      &__info {
        position: absolute;
        bottom: 0;
        right: 0;
        display: flex;
        .logo {
          img {
            width: 80px;
            margin-right: 20px;
          }
        }
        .info {
        }
      }
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
  font-size: 16px;
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

<template>
  <div class="wrapper">
    <div class="pc" :style="{ backgroundImage: `url(${backgroundImagePc})`}">
      <div class="sp" :style="{ backgroundImage: `url(${backgroundImageSp})`}">
        <Header />
        <div class="container">
          <Background :asset="backgroundImage.top"/>
          <!-- <Background :asset="backgroundImage.bottom"/> -->
          <TopArea />
          <FadeIn>
            <SubArea :title="'Markets Supported'" :id="'markets'">
              <Logos :items="markets"/>
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Technologies'" :id="'technologies'">
              <Logos :items="technologies"/>
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Case Studies'" :id="'casestudies'">
              <Works :items="works"/>
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Team'" :id="'team'">
              <Teams :items="teams"/>
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Contact'" :id="'contact'">
              <Contacts :items="contacts"/>
            </SubArea>
            <p class="message">
              - まずは気軽に相談してください✌️
            </p>
          </FadeIn>

        </div>
        <Footer />
      </div>
    </div>
  </div>
</template>

<script>
import Background from '~/components/index/Background.vue';
import TopArea from '~/components/index/TopArea.vue';
import SubArea from '~/components/index/SubArea.vue';
import Logos from '~/components/index/Logos.vue';
import Works from '~/components/index/Works.vue';
import Teams from '~/components/index/Teams.vue';
import Contacts from '~/components/index/Contacts.vue';

// fade in animation
import FadeIn from '~/components/FadeIn.vue';


export default {
  components: {
    TopArea,
    SubArea,
    Logos,
    Works,
    Teams,
    Contacts,
    Background,
    FadeIn,
  },
  methods: {
  },
  data() {
    return {
      backgroundImage: {
        top: {
          path: require('@/assets/img/back_1.png'),
          area: 'top'
        },
        bottom: {
          path: require('@/assets/img/back_2.png'),
          area: 'bottom'
        }
      },
      backgroundImagePc: require('@/assets/img/graph.png'),
      backgroundImageSp: require('@/assets/img/graph_sp.png'),
      markets: [
        {
          src: require('@/assets/img/logos/opensea.png'),
          alt: 'opensea'
        },
        {
          src: require('@/assets/img/logos/rariable.png'),
          alt: 'Rariable'
        },
      ],
      technologies: [
        {
          src: require('@/assets/img/logos/openzeppelin.png'),
          alt: 'OpenZeppelin'
        },
        {
          src: require('@/assets/img/logos/solidity.png'),
          alt: 'Solidity'
        },
        {
          src: require('@/assets/img/logos/ethereum.png'),
          alt: 'Ethereum'
        },
      ],
      works: [
        {
          img: {
            src: require('@/assets/img/works/tinydinoclub.jpg'),
            alt: 'Tiny Dino Club / Generative'
          },
          title: 'Tiny Dino Club / Generative',
          link: 'https://opensea.io/collection/tiny-dino-club-generative',

          desc: '1,000 items | 5.2ETH'
        },
        {
          img: {
            src: require('@/assets/img/works/circlecircle.png'),
            alt: 'Circle Circle'
          },
          title: 'Circle Circle',
          link: 'https://opensea.io/collection/beautiful-circle-circle',
          desc: '1,000 items | 0.0ETH'
        }
      ],
      teams: [
        {
          img: {
            src: require('@/assets/img/team/dofuta.jpg'),
            alt: 'Taisei Dofuku'
          },
          role: 'Engineer',
          title: 'aoiefk',
          desc: 'Web上での表現を得意とする。<br/>カレーが好き。',
          tw: 'https://twitter.com/dofu_kun',
        },
        {
          img: {
            src: require('@/assets/img/team/sk.jpg'),
            alt: 'Taisei Dofuku'
          },
          role: 'Engineer',
          title: 'Shogo Kagiya',
          desc: 'ブロックチェーンエンジニア。<br/>CとPythonを使いこなす。',
          tw: 'https://example.com/',
          fb: 'https://example.com/',
        }
      ],
      contacts: [
        {
          img: {
            src: require('@/assets/img/sns/tw.png'),
            w: 25,
            h: 20,
          },
          text: 'Twitterからお問い合わせ',
          link: 'https://example.com/',
          color: '#00A9F4',
        },
        {
          img: {
            src: require('@/assets/img/sns/dc.png'),
            w: 20,
            h: 20,
          },
          text: 'Discordからお問い合わせ',
          link: 'https://discord.gg/pyVXrd2xXY',
          color: '#5769EA',
        },
        // {
        //   img: {
        //     src: require('@/assets/img/sns/tw.png'),
        //     w: 20,
        //     h: 20,
        //   },
        //   text: 'Instagramからお問い合わせ',
        //   link: 'https://example.com/',
        //   color: '#1E9BEF',
        // }
      ],
    }
  },
  head() {
    const title = 'n42'
    const desc = 'n42は、NFTコレクションの生成と出品の代行サービスを提供しています。'
    return {
      title: title,
      meta: [
        { hid: 'description', name: 'description', content: desc },
        { hid: 'og:title', property: 'og:title', content: title },
        { hid: 'og:description', property: 'og:description', content: desc },
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
  .wrapper {
    .pc {
      background-size: contain;
      background-repeat: no-repeat;
      @media (max-width: $tablet-width) {
        background-size: 0;
      }
    }
    .sp {
      background-size: 0;
      background-repeat: no-repeat;
      @media (max-width: $tablet-width) {
        background-size: contain;
      }
    }
    .container {
      margin-bottom: 100px;
    }
  }
    .message {
      padding: 20px;
      color: $gray;
    }
</style>

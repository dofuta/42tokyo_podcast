<template>
  <div class="wrapper">
    <div class="pc" :style="{ backgroundImage: `url(${backgroundImagePc})`}">
      <div class="sp" :style="{ backgroundImage: `url(${backgroundImageSp})`}">
        <Header />
        <div class="container">
          <TopArea />
          <FadeIn>
            <SubArea :title="'Numbers'" :id="'numbers'">
              <Numbers :items="numbers"/>
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Platforms'" :id="'platforms'">
              <Logos :items="platforms"/>
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Team'" :id="'team'">
              <Teams :items="teams"/>
            </SubArea>
          </FadeIn>
          <!--
          <FadeIn>
            <SubArea :title="'Contact'" :id="'contact'">
              <Contacts :items="contacts"/>
            </SubArea>
            <p class="message">
              - まずは気軽に相談してください✌️
            </p>
          </FadeIn>
          -->
        </div>
        <Footer />
      </div>
    </div>
  </div>
</template>

<script>
import TopArea from '~/components/index/TopArea.vue';
import SubArea from '~/components/index/SubArea.vue';
import Logos from '~/components/index/Logos.vue';
import Teams from '~/components/index/Teams.vue';
import Numbers from '~/components/index/Numbers.vue';
import Contacts from '~/components/index/Contacts.vue';

// fade in animation
import FadeIn from '~/components/FadeIn.vue';


export default {
  components: {
    TopArea,
    SubArea,
    Logos,
    Teams,
    Numbers,
    Contacts,
    FadeIn,
  },
  methods: {
  },
  data() {
    return {
      backgroundImagePc: require('@/assets/img/graph.png'),
      backgroundImageSp: require('@/assets/img/graph_sp.png'),
      platforms: [
        {
          src: require('@/assets/img/logos/spotify.png'),
          alt: 'Spotify'
        },
        {
          src: require('@/assets/img/logos/apple.png'),
          alt: 'Apple'
        },
      ],
      Numbers: [
        {
          title: '『NFT福袋2022 販売までの40時間の戦い』をnoteに公開しました。',
          thumbnail: require('@/assets/img/numbers/nft2022.jpg'),
          link: 'https://note.com/nfourtwo/n/nfbb846f52c74',
          date: '2022.01.05'
        },
        {
          title: '『Generative NFT Collection の作り方』をnoteに公開しました。',
          thumbnail: require('@/assets/img/numbers/tdc.jpg'),
          link: 'https://note.com/aoiefk/n/n5f4576bdc8b9',
          date: '2021.10.15'
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
          link_pc: 'https://twitter.com/n42_official',
          link_sp: 'https://twitter.com/messages/compose?recipient_id=1455754052868788224',
          color: '#00A9F4',
        },
        {
          img: {
            src: require('@/assets/img/sns/dc.png'),
            w: 20,
            h: 20,
          },
          text: 'Discordからお問い合わせ',
          link_pc: 'https://discord.gg/pyVXrd2xXY',
          link_sp: 'https://discord.gg/pyVXrd2xXY',
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
    const title = 'Hello Wolrd - 42 Tokyo'
    const desc = 'Hello Wolrd - 42 Tokyo は、プログラミングと42 Tokyoのそこ知れぬ魅力に迫るべく、 生徒の我々が勝手に始めた皆さんと作るラジオ番組です。'
    return {
      title: title,
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        { hid: 'description', name: 'description', content: desc },
        { hid: 'og:title', property: 'og:title', content: title },
        { hid: 'og:description', property: 'og:description', content: desc },
        { hid: 'og:site_name', property: 'og:site_name', content: title },
        { hid: 'og:type', property: 'og:type', content: 'website' },
        { hid: 'og:url', property: 'og:url', content: 'https://nfourtwo.com' },
        { hid: 'og:image', property: 'og:image', content: '' },
        { name: 'twitter:card', content: 'summary' },
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

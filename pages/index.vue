<template>
  <div class="wrapper">
    <div class="pc" :style="{ backgroundImage: `url(${backgroundImagePc})`}">
      <div class="sp" :style="{ backgroundImage: `url(${backgroundImageSp})`}">
        <Header />
        <div class="container">
          <TopArea />
          <FadeIn>
            <SubArea :title="'Topics'" :id="'topics'">
              <Topics :items="topics"/>
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Numbers'" :id="'numbers'">
              <Numbers :items="numbers"/>
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Platforms'" :id="'platforms'">
              <Logos :items="platforms"/>
              ※準備中です。しばらくは、42 Tokyo キャンパス内部でクローズド配信します。
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Teams'" :id="'team'">
              <Teams :items="teams"/>
            </SubArea>
          </FadeIn>
          <FadeIn>
            <SubArea :title="'Join Our Community'" :id="'join'">
              <Contacts :items="contacts"/>
            </SubArea>
            <p class="message">
              <!-- メッセージが入ります。 -->
            </p>
          </FadeIn>
        </div>
        <Footer />
      </div>
    </div>
  </div>
</template>

<script>
import TopArea from '~/components/index/TopArea.vue';
import SubArea from '~/components/index/SubArea.vue';
import Topics from '~/components/index/Topics.vue';
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
    Topics,
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
      topics: [
        {
          title: "THE FIRST TOUCH<br class='only_sp'/> 〜初めてプログラミングに触れた瞬間〜",
          desc: 'ゲストにお呼びしたプログラマー・エンジニアが初めてプログラミングに触れた時のエピソードを伺っていきます。どんなエンジニアも初めはエンジニアじゃなかった。'
        },
        {
          title: 'わたしのマスト・インストール',
          desc: '知って良かったコマンドから、便利なツールやライブラリ、アプリ、はたまた日用品まで、ゲストの「マストインストール」を聞いていく企画です。知らなかった便利tipsが見つかるかも?',
        },
        {
          title: '42 Tokyoのハナシ',
          desc: '42 Tokyoでの学生生活から、入学を決めたきっかけ、今後の活動まで伺っていきます。謎の多いエンジニア養成機関、42 Tokyoのリアルな学生生活に迫ります。',
        },
      ],
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
      numbers: [
        {
          title: '🎮 #1 ゲスト hkamiyaさん / 42 Tokyo 学生',
          thumbnail: require('@/assets/img/numbers/01.jpg'),
          link: 'https://soundcloud.com/user-159085754/1-hkamiya/s-u6tNrs2eAjU?si=b370dc27bcab417c94af06f085d10646&utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing',
          date: '2022.01.22'
        },
        // {
        //   title: '『Generative NFT Collection の作り方』をnoteに公開しました。',
        //   thumbnail: require('@/assets/img/numbers/tdc.jpg'),
        //   link: 'https://note.com/aoiefk/n/n5f4576bdc8b9',
        //   date: '2021.10.15'
        // }
      ],
      teams: [
        {
          img: {
            src: require('@/assets/img/teams/raida.jpeg'),
            alt: 'raida'
          },
          role: 'パーソナリティー',
          title: 'raida',
          desc: 'ポッドキャスト「0から始めるエンジニア」を運営している。42 Tokyo 学生。',
          tw: 'https://twitter.com/Raida042',
        },
        {
          img: {
            src: require('@/assets/img/teams/dofuku.jpg'),
            alt: 'tdofuku'
          },
          role: 'パーソナリティー',
          title: 'tdofuku',
          desc: 'Web領域全般を担当。42 Tokyo 学生。',
          tw: 'https://twitter.com/TDofuku',
        },
        {
          img: {
            src: require('@/assets/img/teams/kenta.jpeg'),
            alt: 'kentakah'
          },
          role: 'パーソナリティー・企画',
          title: 'kentakah',
          desc: 'コピー・企画・渉外を担当。42 Tokyo 学生。',
          tw: 'https://twitter.com/tkhshknt',
        },
        {
          img: {
            src: require('@/assets/img/teams/anonymous_white.png'),
            alt: '???'
          },
          role: '???',
          title: '???',
          desc: '一緒にラジオを作ってくれる人を募集中です！',
          tw: 'https://twitter.com/hw42tokyo',
        },
      ],
      contacts: [
        {
          img: {
            src: require('@/assets/img/sns/tw.png'),
            w: 25,
            h: 20,
          },
          text: 'Twitterをフォローする',
          link_pc: 'https://twitter.com/hw42tokyo',
          link_sp: 'https://twitter.com/hw42tokyo',
          color: '#00A9F4',
        },
        {
          img: {
            src: require('@/assets/img/sns/dc.png'),
            w: 20,
            h: 20,
          },
          text: 'Discordに参加する',
          link_pc: 'https://discord.gg/uuNRstFc',
          link_sp: 'https://discord.gg/uuNRstFc',
          color: '#5769EA',
        },
      ],
    }
  },
  head() {
    const title = 'Hello Wolrd - 42 Tokyo'
    const desc = 'Hello Wolrd - 42 Tokyo は、プログラミングと42 Tokyoのそこ知れぬ魅力に迫るべく、 学生の我々が勝手に始めた皆さんと作るラジオ番組です。'
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

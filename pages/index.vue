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
              <!-- ※準備中です。しばらくは、42 Tokyo キャンパス内部でクローズド配信します。</br> -->
              <!-- ※Getting Ready. We will be providing podcasts only in the 42 Tokyo campus for the time being. -->
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
          <FadeIn>
            <SubArea :title="'About 42 Tokyo'" :id="'42'">
              <Abouts :items="abouts"/>
            </SubArea>
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
import Abouts from '~/components/index/Abouts.vue';

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
    Abouts,
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
          alt: 'Spotify',
          url: 'https://open.spotify.com/show/1SF8JFcX9LMqPVo6IEu5GY'
        },
        {
          src: require('@/assets/img/logos/apple.png'),
          alt: 'Apple',
          url: 'https://podcasts.apple.com/us/podcast/hello-world-42tokyo/id1612773505'
        },
        {
          src: require('@/assets/img/logos/soundcloud.png'),
          alt: 'SoundCloud',
          url: 'https://soundcloud.com/user-159085754'
        }
      ],
      numbers: [
        {
          title: '🔰 #0 学生ポッドキャスト、はじめました。',
          thumbnail: require('@/assets/img/numbers/00.jpg'),
          link: 'https://soundcloud.com/user-159085754/ibwbthvujypa?utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing',
          date: '2022.03.04'
        },
        // {
        //   title: '⚾️ #3 ゲスト ytaiseiさん / 42 Tokyo 学生',
        //   thumbnail: require('@/assets/img/numbers/03.jpg'),
        //   link: 'https://soundcloud.com/user-159085754/3-ytaisei-42tokyo',
        //   date: '2022.03.04'
        // },
        // {
        //   title: '🚃 #2 ゲスト dhasegawさん / 42 Tokyo 学生',
        //   thumbnail: require('@/assets/img/numbers/02.jpg'),
        //   link: 'https://soundcloud.com/user-159085754/2-dhasegaw-42tokyo?si=883b48977eba4ffdb14c22b23054322d&utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing',
        //   date: '2022.02.16'
        // },
        // {
        //   title: '🎮 #1 ゲスト hkamiyaさん / 42 Tokyo 学生',
        //   thumbnail: require('@/assets/img/numbers/01.jpg'),
        //   link: 'https://soundcloud.com/user-159085754/1-hkamiya/s-u6tNrs2eAjU?si=b370dc27bcab417c94af06f085d10646&utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing',
        //   date: '2022.01.22'
        // },
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
            alt: 'Monesynth Dofuku'
          },
          role: 'パーソナリティー',
          title: 'Monesynth Dofuku',
          desc: 'Web領域全般を担当。42 Tokyo 学生。',
          tw: 'https://twitter.com/mdofuku',
        },
        {
          img: {
            src: require('@/assets/img/teams/kenta.jpeg'),
            alt: 'Kenta A. Takahashi'
          },
          role: 'パーソナリティー・企画',
          title: 'Kenta A. Takahashi',
          desc: 'コピー・企画・渉外を担当。普段は広告屋さんプロデューサー。42 Tokyo 学生。',
          tw: 'https://twitter.com/tkhshknt',
        },
        {
          img: {
            src: require('@/assets/img/teams/kawano.jpeg'),
            alt: 'kawano'
          },
          role: 'キャスティング',
          title: 'kkawano',
          desc: 'Hello Worldのキャスティングを担当。六本木校舎にパワーラックを導入。42 Tokyo 学生。',
          tw: 'https://twitter.com/retriver_42',
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
          link_pc: 'https://discord.gg/E9er6NFhAg',
          link_sp: 'https://discord.gg/E9er6NFhAg',
          color: '#5769EA',
        },
      ],
      abouts: [
        {
          desc: '42 Tokyo（フォーティーツー）は、フランス発のエンジニア養成機関です。アメリカ・シリコンバレーをはじめ、世界各国に教育を展開しています。完全無料で、革新的なカリキュラムを学習可能。プログラミングを学びたい世界中の学生たちが、今この瞬間も42でスキルを磨いています。'
        },
      ],
    }
  },
  head() {
    const title = 'Hello World - 42 Tokyo'
    const desc = 'Hello World - 42 Tokyo は、プログラミングと42 Tokyoのそこ知れぬ魅力に迫るべく、 学生の我々が勝手に始めた皆さんと作るラジオ番組です。'
    const ogimg = 'https://helloworld.42tokyo.jp/ogp.png'
    const url = 'https://helloworld.42tokyo.jp'
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
        { hid: 'og:url', property: 'og:url', content: url },
        { hid: 'og:image', property: 'og:image', content: ogimg },
        { hid: 'twitter:card', name: 'twitter:card', content: 'summary_large_image' },
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

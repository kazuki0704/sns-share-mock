<template>
  <v-app>
    <v-container>
      <v-row justify="center">
        <img :src="require('./assets/bunner.png')" width="375" height="450" />
      </v-row>
      <v-row justify="center" class="ma-5"> </v-row>
      <v-row justify="center" class="ma-5">
        <img
          :src="require('./assets/twitter_share.png')"
          width="240"
          height="54"
          @click="onClickTwitter"
        />
      </v-row>
      <v-row justify="center" class="ma-5">
        <img
          :src="require('./assets/line_share.png')"
          width="240"
          height="54"
          @click="onClickLine"
        />
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    twitterMsg:
      "%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%81%94%E6%8B%9B%E5%BE%85%E2%99%AA%0D%0A%E5%8F%82%E5%8A%A0%E3%81%97%E3%81%A6%E5%95%86%E5%93%81%E3%82%92GET%E3%81%97%E3%82%88%E3%81%86%EF%BC%81%0D%0A%0D%0A%23%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%83%80%E3%82%B0%EF%BC%91+%23%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E3%82%BF%E3%82%B0%EF%BC%92%0D%0A%0D%0A%E2%86%93%E8%A9%B3%E3%81%97%E3%81%8F%E3%81%AF%E3%81%93%E3%81%A1%E3%82%89%E2%86%93%0D%0Ahttps%3A%2F%2Fliff-demo-bfd0c.web.app%2Fshare002.html",
    lineMSG:
      "%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E3%81%94%E6%8B%9B%E5%BE%85%E2%99%AA%0D%0A%E5%8F%82%E5%8A%A0%E3%81%97%E3%81%A6%E5%95%86%E5%93%81%E3%82%92GET%E3%81%97%E3%82%88%E3%81%86%EF%BC%81%0D%0A%0D%0A%E2%86%93%E8%A9%B3%E3%81%97%E3%81%8F%E3%81%AF%E3%81%93%E3%81%A1%E3%82%89%E2%86%93%0D%0Ahttps%3A%2F%2Fliff-demo-bfd0c.web.app%2Fshare001.html"
  }),

  methods: {
    onClickTwitter() {
      this.clickURLEvent("twitter://post?message=" + this.twitterMsg);
    },
    onClickLine() {
      this.clickURLEvent("https://line.me/R/msg/text/?" + this.twitterMsg);
    },
    clickURLEvent(url) {
      const e = document.createEvent("MouseEvents"),
        a = document.createElement("a");
      e.initEvent("click");
      a.href = url;
      a.dispatchEvent(e);
    }
  }
};
</script>

<style lang="sass">
.img
  width: 240px
</style>

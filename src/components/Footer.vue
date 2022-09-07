<template>
  <v-footer dark padless>
    <v-card flat tile class="secondary white--text text-center">
      <v-card-text>
        <v-btn
          v-for="(icon, i) in icons"
          :key="i"
          class="mx-4 white--text"
          :href="icon.link"
          target="_blank"
          icon
        >
          <v-icon size="24px">{{ icon.text }}</v-icon>
        </v-btn>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>Icha Cahya Wulan</strong> | Designed by Joabson Arley
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<style scoped>
.v-card {
  width: 100%;
}
</style>

<script>
export default {
  data: () => ({
    icons: [
      {
        text: "mdi-linkedin",
        link: "https://www.linkedin.com/in/icha-cahya-wulan-889056132/",
      },
      {
        text: "mdi-github",
        link: "https://github.com/ichacahyawulan",
      },
      {
        text: "mdi-instagram",
        link: "https://instagram.com/ichacahyaw/",
      },
    ],
  }),
};
</script>

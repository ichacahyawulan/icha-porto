<template>
  <section id="home">
    <v-parallax dark src="@/assets/img/bgSky1.png" height="750">
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row align="center" justify="center">
            <v-col cols="12" md="8" xl="10" align="center">
              <h1 class="display-1 mb-2">Hi! My Name is</h1>
              <h1 class="display-2 font-weight-bold mb-4">Icha Cahya Wulan</h1>
              <h1 class="font-weight-light">
                I'm an enthusiastic front-end developer from Bandung, Indonesia. 
                Front-end frameworks such as React and VueJS are familiar to me. 
                I enjoy programming and want to learn more about web development.
              </h1>
              <v-btn
                rounded
                outlined
                large
                dark
                href="https://drive.google.com/file/d/108CASEWKL6_nO7r7otMgKILogBbMmdZN/view?usp=sharing"
                target="_blank"
                class="mt-5"
              >
                View My CV
                <v-icon class="ml-2">mdi-open-in-new</v-icon>
              </v-btn>
            </v-col>
            <v-col cols="12" md="6" xl="4" class="hidden-sm-and-down"> </v-col>
          </v-row>
        </v-col>
      </v-row>
      <div class="svg-border-waves text-white">
        <v-img src="@/assets/img/borderWaves.svg" />
      </div>
    </v-parallax>
    <v-container fluid id="tools" class="mt-2">
      <v-row align="center" justify="center">
        <v-col cols="10" align="center">
          <h1 class="display-2 font-weight-light ma-4">Tools</h1>
          <p class="headline font-weight-light ma-4">Here are a few technologies that I've used in my work.</p>
        </v-col>
        <v-col cols="10">
          <v-row align="center" justify="space-around">
            <v-col
              cols="12"
              sm="4"
              class="text-center"
              v-for="(feature, i) in features"
              :key="i"
            >
                <v-tooltip right>
                  <template v-slot:activator="{ on, attrs }">
                    <v-img
                      :src="feature.img"
                      max-width="100px"
                      class="d-block ml-auto mr-auto"
                      :class="{ 'zoom-efect': hover }"
                      v-bind="attrs"
                      v-on="on"
                    ></v-img>
                  </template>
                  <span>{{ feature.title }}</span>
                </v-tooltip>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <div class="svg-border-waves">
      <img src="~@/assets/img/wave2.svg" />
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      features: [
        {
          img: require("@/assets/img/logo_vue.png"),
          title: "VueJS"
        },
        {
          img: require("@/assets/img/logo_react.png"),
          title: "React"
        },
        {
          img: require("@/assets/img/logo_vuetify.png"),
          title: "Vuetify"
        },
        {
          img: require("@/assets/img/logo_bootstrap.png"),
          title: "Bootstrap"
        },
        {
          img: require("@/assets/img/logo_redux.png"),
          title: "Redux"
        },
        {
          img: require("@/assets/img/logo_nodejs.png"),
          title: "NodeJS"
        },
        {
          img: require("@/assets/img/logo_postgresql.png"),
          title: "Postgresql"
        },
        {
          img: require("@/assets/img/logo_leaflet.png"),
          title: "LeafletJS"
        },
        {
          img: require("@/assets/img/logo_geoserver.png"),
          title: "Geoserver"
        },
      ],
    };
  }
};
</script>

<style>
.svg-border-waves .v-image {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3rem;
  width: 100%;
  overflow: hidden;
}

#home {
  z-index: 0;
}

.svg-border-waves img {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  margin-bottom: -2px;
  z-index: -1;
}
</style>

<style>
section {
  position: relative;
}
</style>

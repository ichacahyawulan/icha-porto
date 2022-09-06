<template>
  <section id="project">
    <v-container fluid>
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row align="center" justify="center">
            <v-col cols="12" align="center">
              <h1 class="font-weight-light display-2 ma-4">Project</h1>
              <h1 class="font-weight-light headline mb-6">
                Here are some of the projects I've built.
              </h1>
              <v-row align="center" justify="center">
                <v-col cols="12">
                  <v-row align="center" justify="space-around">
                    <v-col
                      cols="12"
                      sm="3"
                      class="text-center"
                      v-for="(feature, i) in features"
                      :key="i"
                    >
                      <v-hover v-slot:default="{ hover }">
                        <v-card
                          class="card"
                          shaped
                          :elevation="hover ? 10 : 4"
                          :class="{ up: hover }"
                        >
                          <v-img
                            :src="feature.img"
                            max-width="250px"
                            height= "130px"
                            class="d-block ml-auto mr-auto"
                            :class="{ 'zoom-efect': hover }"
                          ></v-img>
                          <h1 class="font-weight-regular title">{{ feature.title }}</h1>
                          <v-btn
                            rounded
                            outlined
                            large
                            light
                            @click="dialog = true, itemID = i"
                          >
                            Details
                          </v-btn>
                        </v-card>
                      </v-hover>
                    </v-col>
                  </v-row>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <v-dialog v-model="dialog" max-width="800px">
      <v-card>
        <v-toolbar
          dark
          color="#283E79"
        >
          <v-toolbar-title>{{ features[itemID].title }}</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn
            icon
            dark
            @click="dialog = false"
          >
            <v-icon>mdi-close</v-icon>
          </v-btn>
        </v-toolbar>
        <v-carousel
          cycle
          height="auto"
          hide-delimiters
        >
          <v-carousel-item
            v-for="(item,i) in details[itemID].img"
            :key="i"
          >
            <v-img v-if="itemID == 2" :src="item" aspect-ratio="2.3"></v-img>
            <v-img v-else :src="item" aspect-ratio="2"></v-img>
            <v-card 
              color="black" 
              class="rounded-0 white--text text-center subtitle-1" 
              style="opacity: 0.3"
            >
              {{i+1}} / {{details[itemID].img.length}}
            </v-card>
          </v-carousel-item>
        </v-carousel>
        <v-card-text class="mt-4" style="color: #171b34;">
          <v-text class="font-weight-bold subtitle-2">Featured Project</v-text>
          <br />
          <v-text class="font-weight-regular subtitle-1"><strong>Desc: </strong> {{details[itemID].desc}}</v-text>
          <br />
          <br />
          <v-text class="subtitle-1"><strong>My Contribution:</strong></v-text>
          <v-text v-html="details[itemID].contribution"></v-text>
        </v-card-text>
        <div class="text-center">
          <v-btn
            v-if="details[itemID].url"
            rounded
            outlined
            light
            :href="details[itemID].url"
            target="_blank"
            class="ml-6 mb-8"
          >
            View Project
          </v-btn>
        </div>
        
      </v-card>
    </v-dialog>
  </section>
</template>

<script>
export default {
  data() {
    return {
      itemID: 0,
      dialog: false,
      features: [
        {
          img: require("@/assets/img/picVoyagee.png"),
          title: "Voyagee Travel News Website"
        },
        {
          img: require("@/assets/img/picMonitoring.png"),
          title: "Task Monitoring System"
        },
        {
          img: require("@/assets/img/picMap.png"),
          title: "Interactive Map Component"
        },
        {
          img: require("@/assets/img/picMapTA.png"),
          title: "Final Project"
        },
      ],
      details: [
        {
          img: [
            require("@/assets/img/picVoyagee.png"),
            require("@/assets/img/picVoyagee1.png"),
            require("@/assets/img/picVoyagee2.png"),
            require("@/assets/img/picVoyagee3.png"),
            require("@/assets/img/picVoyagee4.png"),
            require("@/assets/img/picVoyagee5.png"),
            require("@/assets/img/picVoyagee6.png"),
          ],
          desc: "A simple website that provides travel-related news. Users can save news and also share news on social media. There are several news categories that can make it easier for users to choose which news to read.",
          contribution: `
            <ul>
              <li>Create a login and sign-up page.</li>
              <li>Create a destination slide group and the most recent news card on the landing page.</li>
              <li>Create a page containing a list of news and a page displaying news details.</li>
              <li>Develop a feature that displays the number of news views, allows users to share the news, and allows users to save and delete saved news.</li>
              <li>Performing a stress test with k6.</li>
              <li>Tools used: <strong>VueJS, Vuetify, NodeJS, PostgreSQL.</strong></li>
            </ul>
            `,
          url: "https://voyagee-news.vercel.app/"
        },
        {
          img: [
            require("@/assets/img/picMonitoring.png"),
            require("@/assets/img/picMonitoring1.png"),
            require("@/assets/img/picMonitoring2.png"),
            require("@/assets/img/picMonitoring3.png"),
            require("@/assets/img/picMonitoring4.png"),
            require("@/assets/img/picMonitoring5.png"),
            require("@/assets/img/picMonitoring6.png"),
            require("@/assets/img/picMonitoring7.png"),
            require("@/assets/img/picMonitoring8.png"),
          ],
          desc: "A monitoring system on the campus academic website helps monitor the progress of student assignments. There are several features for both lecturers and students. Lecturers can add tasks and see the progress of each student's work. Meanwhile, students can keep track of the progress of the tasks given by the lecturer.",
          contribution: `
            <ul>
              <li>Led the monitoring team.</li>
              <li>Create a dashboard that displays each student's progress in completing tasks.</li>
              <li>Create the main page, which includes a list of the lecturer's classes and courses.</li>
              <li>Create a page with a list of tasks for each course and features for adding tasks.</li>
              <li>Create a page that lists the subtasks of a task and features for adding and editing subtasks.</li>
              <li>Create a page with information about the task that the students completed.</li>
              <li>Tools used: <strong>VueJS, Vuetify, NodeJS, PostgreSQL.</strong></li>
            </ul>
            `
        },
        {
          img: [
            require("@/assets/img/picMap1.png"),
            require("@/assets/img/picMap2.png"),
            require("@/assets/img/picMap3.png"),
            require("@/assets/img/picMap4.png"),
            require("@/assets/img/picMap5.png"),
            require("@/assets/img/picMap6.png"),
            require("@/assets/img/picMap7.png"),
            require("@/assets/img/picMap8.png"),
            require("@/assets/img/picMap9.png"),
            require("@/assets/img/picMap10.png"),
            require("@/assets/img/picMap11.png"),
            require("@/assets/img/picMap12.png"),
            require("@/assets/img/picMap13.png"),
            require("@/assets/img/picMap14.png"),
            require("@/assets/img/picMap15.png"),
            require("@/assets/img/picMap16.png"),
            require("@/assets/img/picMap17.png"),
            require("@/assets/img/picMap18.png"),
            require("@/assets/img/picMap19.png"),
            require("@/assets/img/picMap20.png"),
            require("@/assets/img/picMap21.png"),
            require("@/assets/img/picMap22.png")
          ],
          desc: "A map component is used in an information system to visualize various data. The data displayed include regional boundaries, weather, and aircraft position movements.",
          contribution: `
            <ul>
              <li>Create interactive maps that can display various information.</li>
              <li>Create a sidebar component containing selectable information to display on the map.</li>
              <li>Tools used: <strong>React, Redux, Bootstrap, LeafletJS, Socket.IO, PostgreSQL, PostGIS, QGIS, GeoServer.</strong></li>
            </ul>
            `
        },
        {
          img: [
            require("@/assets/img/picMapTA.png"),
            require("@/assets/img/picMapTA1.png")
          ],
          desc: "Analysis of Grid-based Selection Implementation in Data Visualization for Vessel Position Monitoring on Maps is the title of the final project. The study was carried out to analyze methods for improving the performance of data visualization on maps.",
          contribution: `
            <ul>
              <li>Perform research to find the most effective approach.</li>
              <li>Develop a map component as a media for visualizing ship data.</li>
              <li>Visualize the movement of the ship's position on the map.</li>
              <li>Doing experiments.</li>
              <li>Analyzing experimental results.</li>
              <li>Tools used: <strong>React, LeafletJS, Socket.IO, NodeJS, PostgreSQL</strong></li>
            </ul>
            `
        }
      ],
    };
  }
};
</script>

<style scoped>
#project {
  background-color: #f4f7f5;
}

.card {
  min-height: 300px;
  padding: 10px;
  transition: 0.5s ease-out;
}

.card .v-image {
  margin-bottom: 15px;
  transition: 0.75s;
}

.card h1 {
  margin-bottom: 10px;
}

.zoom-efect {
  transform: scale(1.1);
}

.up {
  transform: translateY(-20px);
  transition: 0.5s ease-out;
}
</style>

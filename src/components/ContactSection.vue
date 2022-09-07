<template>
  <section class="pb-8" id="contact">
    <v-container fluid>
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row justify="center">
            <v-col cols="12" sm="8" align="center">
              <h1 class="font-weight-light display-2 ma-4">Contact</h1>
              <h3 class="font-weight-light mt-3">
                I am currently open to all opportunities, especially those that 
                involve front-end development. If you have any requests or questions, 
                please contact me using the information provided below.
              </h3>
              <h3 class="font-weight-light mt-3">
                Email: ichacahyawulan@gmail.com
              </h3>
              <h3 class="font-weight-light mb-6">
                Phone: +62 819-1056-5352
              </h3>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <div class="svg-border-waves text-white">
      <v-img src="~@/assets/img/borderWavesBlue.svg"/>
    </div>
  </section>
</template>

<style scoped>
#contact {
  background-color: #f4f7f5;
}

.svg-border-waves .v-image {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3rem;
  width: 100%;
  overflow: hidden;
}

</style>

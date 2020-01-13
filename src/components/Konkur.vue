<template>
    <div
    class=" pa-0 ma-0">
        <div 
        class="text-center display-3">
          Konkur
        </div>

        <!-- back card -->
        <v-card
        tile
        class="indigo darken-4 float-up elevation-24 my-5 py-5">
          <v-row
          class="h100 pa-0 ma-0"
          justify="center"
          align="center">

          <!-- illus -->
            <v-col
            cols="12" md="4"
            class="d-flex justify-center align-center ">
              <v-img
              contain
              class="float_down_slow"
              src="../assets/illus/konkur.png">  
              </v-img>
            </v-col>

          <!-- text -->
            <v-col
            cols="12" md="8"
            class="d-flex justify-center float-up-fast">
              <v-card
              class="orange lighten-2 elevation-16  w90"
              height="">
              <v-card-text
              class="indigo--text text--darken-4 title">
                Ad exercitation elit laboris deserunt proident voluptate laboris ut consequat. Elit occaecat qui magna do. Ex qui elit eiusmod ut voluptate. Aute incididunt laboris enim ipsum ea laboris amet qui nulla.
                Ad culpa commodo minim in ut cillum excepteur id minim adipisicing. Voluptate nostrud labore deserunt dolore minim ipsum pariatur est. Fugiat ut duis voluptate ea Lorem elit. Enim proident dolor enim sint minim do voluptate eu irure occaecat aliqua.
              </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-card>

        <v-row 
        class="mx-2"
        justify="center"
        align="center">
          <v-col
          class="d-flex justify-center"
          cols="12" md="4"
          v-for="(item, index) in 3" :key="index">
            <v-card
            falt
            class="indigo darken-3 w100 pa-1">
            <v-card 
            height=""
            class="white w100 ">
            <div
            class="text-center display-2">Gaj</div>
              <v-row
              class="h100 pa-0 ma-0"
              justify="center"
              align="center">
                <v-col
                cols="12"
                class="d-flex justify-center">
                  <v-avatar
                    size="100"
                    tile
                    class=""
                  >
                    <img src="../assets/gaj-log.png" alt="alt">
                  </v-avatar>

                </v-col>
                <v-col>
                  <v-card
                  flat>
                    <v-card-text
                    class="indigo--text text--darken-4 orange lighten-3 body-1">
                      Duis nisi exercitation esse commodo eu esse adipisicing ut mollit amet. Pariatur veniam pariatur et qui quis aliqua mollit irure laboris minim minim tempor. Consectetur laborum esse ullamco ea magna aute et et excepteur laboris ea. Nisi sint aliqua officia consectetur incididunt sunt voluptate aliqua in.
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>

            </v-card>
            </v-card>
          </v-col>
        </v-row>
    </div>
</template>

<script>

export default {
  name: 'App',
  components:{ },

  data: () => ({
      
  }),
};

</script>


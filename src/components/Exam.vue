<template>
    <div
    class=" pa-0 ma-0 w100 ">
        <div 
        class="text-center display-3">
          Exam
        </div>

        <!-- back card -->
        <v-card
        tile
        flat
        
        class=" my-5 py-5">
          <v-row
          class="h100 pa-0 ma-0"
          justify="center"
          align="center">

          <!-- illus -->
            <v-col
            cols="12" md="5"
            class="d-flex justify-center float-illus align-center mx-12">
              <v-img
              contain
              class="float_down_slow mx-12"
              src="../assets/illus/konkur.png">  
              </v-img>
            </v-col>

          <!-- text -->
            <v-col
            cols="12" md="6"
            class="d-flex justify-center">
              <v-card
              max-width="500"
              class="orange lighten-2 pr-3 elevation-24 w90"
              height="">
                <v-card>
                    <v-card-text
                    class="indigo--text text--darken-4 title">
                        Ad exercitation elit laboris deserunt proident voluptate laboris ut consequat. Elit occaecat qui magna do. Ex qui elit eiusmod ut voluptate. Aute incididunt laboris enim ipsum ea laboris amet qui nulla.
                        Ad culpa commodo minim in ut cillum excepteur id minim adipisicing. Voluptate nostrud labore deserunt dolore minim ipsum pariatur est. Fugiat ut duis voluptate ea Lorem elit. Enim proident dolor enim sint minim do voluptate eu irure occaecat aliqua.
                    </v-card-text>
                </v-card>
              </v-card>
            </v-col>
          </v-row>
        </v-card>

        <!-- exam cards -->
        <v-row 
        class="mx-2"
        justify="center"
        align="center">
          <v-col
          class="d-flex justify-center"
          cols="12" md="4"
          v-for="(exam, index) in exams" :key="index">
            <v-card 
            flat
            height=""
            class=" h100 indigo elevation-16 w100 pr-2">
            <v-card
            flat
            class="ma-0 pa-0 h100 w100 pa-1 py-3">
            <div
            class="text-center display-2">{{exam.title}}</div>
                <v-row
                class="h100 pa-0 ma-0"
                justify="center"
                align="center">

                <!-- exam logo -->
                    <v-col
                    cols="12"
                    class="d-flex justify-center">
                    <v-avatar
                        size="100"
                        tile
                        class=""
                    >
                        <img v-if="index == 0" src="../assets/gaj-log.png" alt="alt">
                        <img v-else-if="index == 1" src="../assets/maz-logo.png" alt="alt">
                        <img v-else src="../assets/sanjesh.png" alt="alt">
                        
                    </v-avatar>

                    </v-col>

                    <!-- exam text -->
                    <v-col>
                    <v-card
                    class=""
                    flat>
                        <v-card-text
                        class="indigo--text text--darken-4 orange lighten-3 body-1">
                            {{exam.description}}
                        </v-card-text>
                    </v-card>
                    </v-col>
                </v-row>

                <div
                class="ma-0 pa-0 w100 d-flex justify-start">
                    <a
                    target="_blank"
                    :href="exam.readMore">
                        <v-btn
                        class="indigo orange--text text--lighten-1 ml-3 darken-3">
                            read more
                        </v-btn>
                    </a>
                </div>
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
      exams:[
        {title:'Gaj',description:'Duis nisi exercitation esse commodo eu esse adipisicing ut mollit amet. Pariatur veniam pariatur et qui quis aliqua mollit irure laboris minim minim tempor. Consectetur laborum esse ullamco ea magna aute et et excepteur laboris ea. Nisi sint aliqua officia consectetur incididunt sunt voluptate aliqua in.',logo:'../assets/gaj-log.png',readMore:"http://azmoon.gaj.ir/"},
        {title:'Maz',description:'Duis nisi exercitation esse commodo eu esse adipisicing ut mollit amet. Pariatur veniam pariatur et qui quis aliqua mollit irure laboris minim minim tempor. Consectetur laborum esse ullamco ea magna aute et et excepteur laboris ea. Nisi sint aliqua officia consectetur incididunt sunt voluptate aliqua in.',logo:'../assets/maz-logo.png',readMore:"https://biomaze.ir/"},
        {title:'Sanjesh',description:'Duis nisi exercitation esse commodo eu esse adipisicing ut mollit amet. Pariatur veniam pariatur et qui quis aliqua mollit irure laboris minim minim tempor. Consectetur laborum esse ullamco ea magna aute et et excepteur laboris ea. Nisi sint aliqua officia consectetur incididunt sunt voluptate aliqua in.',logo:'../assets/sanjesh.png',readMore:"http://92.242.195.129/sanjeshserv_regsarasari/"},

      ]
  }),
};

</script>


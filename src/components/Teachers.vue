<template>
    <div
    class="  pa-0 ma-0  w100">
        <div 
        class="text-center w100 display-3 mb-12">
          Teachers
        </div>

        <!-- back card -->
        <v-card
        class="indigo elevation-24 my-5 pl-4 mx-5">
        <v-card
        tile
        flat
        class=" py-5">
          <v-row
          class="h100 pa-0 ma-0"
          justify="center"
          align="center">

          <!-- illus -->
            <v-col
            cols="12" md="4"
            class="d-flex justify-center float-illus mx-5  align-center ">
              <v-img
              contain
              class=""
              src="../assets/illus/hat.png">  
              </v-img>
            </v-col>

          <!-- text -->
            <v-col
            cols="12" md="7"
            class="d-flex justify-center f">
              <v-card
              outlined
              max-width="600"
              class="pr-2 indigo elevation-1">
                <v-card 
                flat
                class="orange lighten-5"
                height="">
                  <v-card-text
                  class="indigo--text text--darken-3 title">
                    Ad exercitation elit laboris deserunt proident voluptate laboris ut consequat. Elit occaecat qui magna do. Ex qui elit eiusmod ut voluptate. Aute incididunt laboris enim ipsum ea laboris amet qui nulla.
                    Ad culpa commodo minim in ut cillum excepteur id minim adipisicing. Voluptate nostrud labore deserunt dolore minim ipsum pariatur est. Fugiat ut duis voluptate ea Lorem elit. Enim proident dolor enim sint minim do voluptate eu irure occaecat aliqua.
                    Ad culpa commodo minim in ut cillum excepteur id minim adipisicing. Voluptate nostrud labore deserunt dolore minim ipsum pariatur est. Fugiat ut duis voluptate ea Lorem elit. Enim proident dolor enim sint minim do voluptate eu irure occaecat aliqua.

                  </v-card-text>
                </v-card>
              </v-card>
            </v-col>
          </v-row>
          </v-card>
        </v-card>
        <v-divider class=" indigo mt-12"></v-divider>
        <div 
        class="text-center w100 display-3 my-12">
          Noor Teachers
        </div>

            <div
            v-for="(teacher, index) in teachers" :key="index"
            class="d-flex justify-center">
              <v-card
              hover
              shaped
              flat
              outlined
              max-width="1000"
              :class="`pr-2 ma-5 ${teacher.color}`">
                <v-card 
                flat
                class=" elevation-0"
                height="">
                <v-card-title
                class="">
                  <v-icon size="100" class="mr-5" :color="teacher.color">mdi-school</v-icon> <span class="headline">{{teacher.title}}</span>
                </v-card-title>
                  <v-card-text
                  class="title">
                    Ad exercitation elit laboris deserunt proident voluptate laboris ut consequat. Elit occaecat qui magna do. Ex qui elit eiusmod ut voluptate. Aute incididunt laboris enim ipsum ea laboris amet qui nulla.
                    Ad culpa commodo minim in ut cillum excepteur id minim adipisicing. Voluptate nostrud labore deserunt dolore minim ipsum pariatur est. Fugiat ut duis voluptate ea Lorem elit. Enim proident dolor enim sint minim do voluptate eu irure occaecat aliqua.
                    Ad culpa commodo minim in ut cillum excepteur id minim adipisicing. Voluptate nostrud labore deserunt dolore minim ipsum pariatur est. Fugiat ut duis voluptate ea Lorem elit. Enim proident dolor enim sint minim do voluptate eu irure occaecat aliqua.
                  </v-card-text>
                </v-card>
              </v-card>
            </div>  
        
    </div>
</template>

<script>

export default {
  name: 'App',
  components:{ },

  data: () => ({
      teachers:[
        {title:'Math',color:'orange'},
        {title:'physics ',color:'indigo'},
        {title:'Chemistry',color:'pink'},

      ]   
  }),

 
};

</script>


<template>
  <div>
<!-- place home page in a grid system -->
  <v-container  fluid fill-height class="white pa-0"> 
    <v-row     
      class="ma-0"
      justify="space-between"
    >



      <!-- hero image -->

        <!-- parallax hero image -->
      <v-col 
      cols="12"
      class="ma-0 pa-0">
           <v-row
            align="center"
            justify="center"
            class="h100 w100 pa-0 ma-0"
          >
          <v-card
          flat
          class="w100"
          :height="parallaxH">
            <v-row
            justify="center"
            align="center"
            class="ma-0 pa-0 w100 h100">
              <v-col 
              cols="6"
              justify-self="start">
                <v-img
                contain
                height="500"
                class="tba"
                src="../assets/illus/undraw_Graduation_ktn0.png">
                <v-row>
                  <v-col class=" mx-12" cols="6"
                  justify-self="end">
                    <h1 class="display-1 font-weight-thin mb-4">Noor Edu Abadan</h1>
                    <h4 class="subheading">enjoy our courses and classes!</h4>        
                  </v-col>
                 </v-row>    
                </v-img>
              </v-col>
        
            </v-row>
          </v-card>  
          </v-row>
      </v-col>





      <!-- section cards use for loop-->
      <v-col
      cols="6" sm="6" md="4" lg="2"
      v-for="(section, index) in sections" :key="index"
      class="ma-0 pa-1 pt-2">
        <v-hover>
          <template v-slot="{ hover }">
            <v-card
              :elevation="hover ? 24 : 8"
              v-resize="onResize"
              :ripple="false"
              :height="cardH"
               @click="dialog =! dialog"
              class=" ma-0 pa-0 w100"
            >
  
                  <div
                  class="d-flex justify-center h100 w100">
                    <v-img
                    contain
                    class="h100 w100"
                    src="../assets/illus/undraw_Graduation_ktn0 (1).png">
                      <v-row
                      justify="center"
                      align="center">
                        <v-col
                        cols="12">
                          <div :class="hover ? 'text--red':'text--blue'"
                          class="text-center font-weight-black">
                            <span >{{section.title}}</span>
                          </div>
                        </v-col>
                        <v-col
                        cols="12">
                          <div 
                          class="text-center font-weight-bold">
                            <span >{{section.description}}</span>
                          </div>
                        </v-col>
                      </v-row>
                    </v-img>
                  </div>
             

            
            </v-card>
          </template>
         </v-hover>
      </v-col>


  <!-- <v-container  fluid fill-height class="white pa-0"> 
    <v-row     
      class="ma-0"
      justify="space-between"
    > -->

      <!-- Description -->
      <v-col class="pink lighten-2 mt-1" 
      >
        <v-row
        justify="center">

          <!-- description title-->
          <v-col  cols="12">
            <div class="text-center">
              <span>Noor For All</span>
            </div>
          </v-col>

          <!-- description (for loop used)-->
          <v-col 
          v-for="(description, index) in 3" :key="index"
          cols="12" sm="6" md="4" lg="3">
            <v-card 
            height="300" 
            class="elevation-24">



            </v-card>
          </v-col>
        </v-row>
      </v-col>




      <!-- proud -->
      <v-col 
      class="pink lighten-3" 
      cols="12">

        <v-row
        justify="space-between">

        <!-- proud title -->
        <v-col  cols="12">
          <div class="text-center">
            <span>It is our honor to be with you</span>
          </div>
        </v-col>
          

          <!-- Proud items (for loop used)-->
          <v-col 
          cols="4" sm="4" md="4" lg="2" 
          v-for="(description, index) in 6" :key="index">
            <v-card 
            class="elevation-24"
            >
              <v-responsive  
              height="100"
              :aspect-ratio="1/1">
              
              hey im a medal
              </v-responsive>
            </v-card>
          </v-col>

        </v-row>
      </v-col>




      <!-- Footer-->
      <v-col cols="12">
        <v-card
        height="300"
        tile>
          hello im a footer
        </v-card>
      </v-col>

    </v-row>




    <!-- Dialog -->
 
      <v-dialog
        fullscreen
        v-model="dialog"
        class=""
        origin=""
      >
        <!-- <template v-slot:activator="{ on }">
          <v-btn
            color="yellow darken-4"
            dark
            v-on="on"
          >
            Click Me
          </v-btn>
        </template> -->


    

        <v-card 
        light
        tile
        class="blue darken-4 op90 h100">
          
        <div
        class="d-flex justify-center"
        absolute
        top>
          <v-btn
          @click="dialog =! dialog"
          flat
          class="blue darken-4 pa-0 ma-0 hidden-xs-only right"
          text
          icon
          large
          absolute
          >
            <v-icon
            color="white"
            >
              mdi-close
            </v-icon>
          </v-btn>
        </div>
   
        </v-card>

      </v-dialog>




  </v-container>
  </div>
</template>

<script>

export default {
  name: 'home',
  data: () =>({   
    //data
    dialog: false,
    parallaxH:0,
    cardH:0,
    cardW:0,
    sections:[
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
    ]
  }),
    mounted () {
      this.onResize()
    },
    //use mixins here
    methods: {
      onResize () {
        if (window.innerWidth >= 1264){ //xlarge & large;
          this.cardH = 200;
          this.parallaxH = 600; 
        }
        else if (window.innerWidth >= 960 && window.innerWidth < 1264){ //medium & small
          this.cardH = 180;
          this.parallaxH = 500;  
        }
        else{ //xsmall adn small
          this.cardH =150;
          this.parallaxH =400; 
        }
        // { x: window.innerWidth, y: window.innerHeight }
      }
}
}
</script>
<style scoped>


</style>

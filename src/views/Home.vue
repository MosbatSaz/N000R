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
            class="ma-0 pa-0 h100">
              <v-col class="text-center" cols="12">
                <h1 class="display-1 font-weight-thin mb-4">Noor Edu</h1>
                <h4 class="subheading">enjoy our courses and classes!</h4>
              </v-col>
            </v-row>
          </v-card>  
          </v-row>
      </v-col>





      <!-- section cards use for loop-->
      <v-col
      cols="6" sm="6" md="4" lg="2"
      v-for="(section, index) in 6" :key="index"
      class="ma-0 pa-1 pt-2">
        <v-hover>
          <template v-slot="{ hover }">
            <v-card
              :elevation="hover ? 24 : 4"
              v-resize="onResize"
              :height="cardH"
               @click="dialog =! dialog"
              class="white ma-0 pa-0 w100"
            >
              Prop based elevation
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
      <v-col class="blue darken-2 mt-1" 
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
              hey im a description
            </v-card>
          </v-col>
        </v-row>
      </v-col>




      <!-- proud -->
      <v-col 
      class="indigo " 
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
        class="indigo darken-2 op90">
          
        <div
        class="d-flex justify-center"
        absolute
        top>
          <v-btn
          @click="dialog =! dialog"
          flat
          class="indigo darken-2 pa-0 ma-0 hidden-xs-only right"
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
                <!-- content will be here -->
                 <component :is="1" ></component>
        <div
      class="d-flex justify-center">
         <v-btn
        @click="dialog =! dialog"
        flat
        class="indigo darken-2 pa-0 ma-0 hidden-sm-and-up right"
        text
        icon
        large
        absolute
        bottom
        height="100"
        width="100"
        >
          <v-icon
          x-large
          height="100"
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
      {name:''}
    ]
  }),
    mounted () {
      this.onResize()
    },

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
#inspire img {
  height: 50%
}
</style>

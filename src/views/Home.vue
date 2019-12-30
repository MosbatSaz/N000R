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
        <v-parallax
          id="inspire"
          dark
          src="../../public/mountain.jpg"
          class="ma-0"
          :height="parallaxH"
        >
          <!-- Slogan slide -->
          <v-row
            align="center"
            justify="center"
          >
            <v-col class="text-center" cols="12">
              <h1 class="display-1 font-weight-thin mb-4">Noor Edu</h1>
              <h4 class="subheading">enjoy our courses and classes!</h4>
            </v-col>
          </v-row>
        </v-parallax>
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
              class="yellow darken-3 ma-0 pa-0 w100"
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
    <v-app-bar
    flat
    fixed
    class="pink pa-0 ma-0 op50"
    height="40">
         <v-btn
        @click="dialog =! dialog"
        large
        tile
        text
        class="pink pa-0 ma-0 w100"
        height="40"
        >
          <v-icon>
            mdi-close
          </v-icon>
        </v-btn>
    </v-app-bar>

    

        <v-card 
        light
        tile
        class="op90">
        <v-card
        tile
        class=""
        height="500"
        color="indigo darken-4">
          <v-card-title
            class="headline"
            primary-title
          >
          
          </v-card-title>

          <v-card-text>
          </v-card-text>

          <!-- <v-divider></v-divider> -->

          <!-- <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              color="primary"
              text
              @click="dialog = false"
            >
              I accept
            </v-btn>
          </v-card-actions> -->
        </v-card>
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
        if (window.innerWidth >= 960){ //xlarge & large
          this.cardW = (20/100)*window.innerWidth-4;
          this.cardH = (20/100)*window.innerHeight;
          this.parallaxH = (80/100)*window.innerHeight; 
        }
        else if (window.innerWidth > 600 && window.innerWidth < 960){ //medium & small
          this.cardW = (33/100)*window.innerWidth-5
          this.cardH = (20/100)*window.innerHeight;
          this.parallaxH = (40/100)*window.innerHeight;  
        }
        else{ //xsmall
          this.cardW = (95/100)*window.innerWidth
          this.cardH = (15/100)*window.innerHeight;
          this.parallaxH = (50/100)*window.innerHeight; 
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

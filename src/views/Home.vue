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
            class="elevation-24 ma-0 pa-0 d-flex ">
              <v-card 
              hover 
              class="h100 w100 ma-5">

              <!-- icon -->
                <div
                class="d-flex justify-center">
                  <v-icon x-large>mdi-evernote</v-icon>
                </div>

              <!-- header -->
                <div
                class="d-flex justify-center">
                  header
                </div>
              <!-- description -->
                <div
                class="d-flex justify-center text-center">
                  Ipsum dolor eiusmod excepteur nulla enim aute aute veniam aute nostrud.
                  Veniam ea ullamco ut laboris pariatur in.
                  Mollit deserunt id nisi mollit ad adipisicing irure esse pariatur et consequat.
                  Ex pariatur tempor sint sit reprehenderit non dolor. Est labore sit aute reprehenderit.
           
                </div>

              </v-card>
            </v-card>
          </v-col>
        </v-row>
      </v-col>




      <!-- proud -->
      <v-col 
      class="pink lighten-3" 
      cols="12">
      <v-row
      justify="center"
      align="center"
      >
        <v-col
        cols="2"
        v-for="(medal, index) in 6" :key="index"
        >
          <!-- title -->
          <div
          class="d-flex justify-center">
            Title
          </div>

          <!-- medal -->
          <div
          class="d-flex justify-center">
            <v-icon>
              mdi-medal
            </v-icon>
          </div>
        </v-col>
      </v-row>  
      </v-col>




      <!-- Footer-->
      <v-col
      class="pa-0" 
      cols="12">
        <v-card
        class="black"
        height="300"
        tile
        dark>
        <!-- footer options ( fops ) -->
        <v-app-bar
        color="blue darken-2"
        flat
        >
          <div
          class="w100 d-flex justify-center">
            <div
            class="w40 d-flex mx-5 justify-space-around">
              <v-btn
              v-for="(fop, index) in 5" :key="index"
              @click="sheet = !sheet"
              rounded
              text>
              click
              </v-btn>
            </div>
          </div>
        </v-app-bar>  

        <!-- Map -->
        <v-hover
        v-slot:default="{ hover }">
            <template>
              <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1721.7875123071194!2d48.28376717599155!3d30.334603710412743!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3fc44f3fa77efb21%3A0xce725c74ec9af253!2sSmoke.Shop!5e0!3m2!1sen!2suk!4v1578238334488!5m2!1sen!2suk"  
              class="w100 h100" 
              frameborder="0" 
              style="border:0;" 
              allowfullscreen="">
              </iframe>
            </template>
        </v-hover>
  


          <v-footer
            padless
            class="w100"
          >
            <v-card
              flat
              tile
              class="blue  darken-4 w100 white--text text-center"
            >
              <v-card-text>
                <v-btn
                  v-for="icon in icons"
                  :key="icon"
                  class="mx-4 white--text"
                  icon
                  large
                >
                  <v-icon size="36px">{{ icon }}</v-icon>
                </v-btn>
              </v-card-text>

              <v-card-text class="white--text pt-0">
              </v-card-text>

              <v-divider></v-divider>

              <v-card-text class="white--text">
                {{ new Date().getFullYear() }} — <strong>Mosbat Saz</strong>
              </v-card-text>
            </v-card>
          </v-footer>

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
        class="blue darken-4 op90">
          
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

        <component :is="c"></component>
   
        </v-card>

      </v-dialog>

      <!-- Bottom sheet -->

      <v-bottom-sheet 
      v-model="sheet" 
      :inset="false" 
      :hide-overlay="hideOverlay"
      >
      <v-sheet class="text-center" height="500">
        <v-btn
          class="my-6"
          depressed
          fab
          color="error"
          @click="sheet = !sheet"
        ><v-icon>mdi-close</v-icon></v-btn>
      </v-sheet>
    </v-bottom-sheet>



  </v-container>
  </div>
</template>

<script>
import Archive from '../components/Archive.vue'
export default {
  name: 'home',

  components:{
    Archive,
  },
  data: () =>({   
    //data
    c : Archive,
    dialog: false,
    sheet: false,
    parallaxH:0,
    cardH:0,
    cardW:0,
    mapFade:true,
    sections:[
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
    ],      
    icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-google-plus',
        'mdi-linkedin',
        'mdi-instagram',
      ],
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

<template>
  <div>
<!-- place home page in a grid system -->
  <v-container  fluid fill-height class="white pa-0"> 
    <v-row     
      class="ma-0"
      justify="space-between"
    >



      <!-- hero image -->

        <!-- hero image -->
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
            tile
            height="800"
            class="w100">

              <!-- display on -->

                <!-- lg and xl -->
                <v-img
                src="../assets/illus/hero-image-back-wide.png"
                class="pa-0 ma-0 h100 w100 hidden-md-and-down">
                </v-img>

                <!-- md and sm -->
                <div
                class="hidden-xs-only h100 w100">
                  <v-img 
                  src="../assets/illus/hero-image-back-md.png"
                  class="pa-0 ma-0 h100 w100 hidden-lg-and-up ">
                  </v-img>
                </div>

                <!-- only xs -->
                <v-img 
                src="../assets/illus/hero-image-back-small.png"
                class="pa-0 ma-0 h100 w100 hidden-sm-and-up">
                </v-img>

            </v-card>  
          </v-row>
      </v-col>


          <!-- HERO QUOET -->
              <!-- <v-row
              justify="center"
              align="center"
              class="ma-0 pa-0 w100 h100">

                <v-col 
                cols="6"
                justify-self="start">
                  <v-img
                  contain
                  height="400"
                  class=""
                  src="../assets/illus/thinking.png">    
                  </v-img>
                </v-col>

                <v-col 
                class="text-right" 
                cols="6"
                justify-self="end">
                <div
                class="text-center">
                  <h1 class="display-1 font-weight-thin mb-4">Noor Edu Abadan</h1>
                  <h4 class="subheading">enjoy our courses and classes!</h4>        
                </div>  
                </v-col>

              </v-row> -->




    
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
                class="h100 w100"
                src="../assets/illus/hero full.png">
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


      <!-- Description -->
      <v-col 
      class="pink lighten-2 pa-0 ma-0" 
      >
        <v-card
        tile
        class="h100 w100 pa-0 py-12 ma-0">
         
            <v-row
            justify="center"
            align="center">

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
                 <v-img
                 class="elevation-16"
                  height="500"
                  src="../assets/illus/doodles-school-0.jpg"
                  >
                  <v-card 
                  class="elevation-8 h80 ma-5 mt-12 pa-0 d-flex ">
                 
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
                </v-img>
              </v-col>

            </v-row>

        </v-card>
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
        color="indigo darken-2"
        flat
        >
          <div
          class="w100 d-flex justify-center">
            <div
            class="w40 d-flex mx-5 justify-space-around">
              <v-btn
              v-for="(fop, index) in fobs" :key="index"
              @click="sheet = !sheet"
              rounded
              text>
              <span>{{fobs.title}}</span>
              <v-icon>{{fobs.icon}}</v-icon>
              </v-btn>
            </div>
          </div>
        </v-app-bar>  

        <!-- Map -->
        <v-hover
        v-slot:default="{ hover }">
            <template>
              <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3443.57502456997!2d48.28267815106922!3d30.33460371167148!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3fc44f12eb39a3c7%3A0xc4ec16f6be22c4da!2sNoor%20Arvand%20Educational%20institution!5e0!3m2!1sen!2s!4v1578324126941!5m2!1sen!2s"
              class="h100 w100"   
              allowfullscreen=""></iframe>
            </template>
        </v-hover>
  


          <v-footer
            padless
            class="w100"
          >
            <v-card
              flat
              tile
              class="indigo darken-4 w100 white--text text-center"
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

              <v-divider></v-divider>

              <v-card-text class="white--text">
                <v-row
                class="mt-n3"
                justify="center"
                align="center"
                >
                  <v-col
                  cols="12">
                    <v-avatar
                    tile
                    size="60"
                    class="mb-n6"
                    >
                      <v-img
                      src="../assets/MosbatSaz +saz-layers.png">
                      </v-img>
                    </v-avatar> 
                  </v-col>
                  <v-cols
                  cols="12">
                    <span
                    class="ml-5 font-weight-light">
                    {{ new Date().getFullYear() }}
                    </span> 
                  </v-cols>
                </v-row>            
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
          
        <!-- <div
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
        </div> -->

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
    fobs:[
      {title:'CEO',icon:'mdi-sofa'},
      {title:'Contact Us',icon:'mdi-phone-classic'},
      {title:'FAQ',icon:'mdi-question'},
      {title:'Comments',icon:'mdi-comment-multiple-outline'},
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

<template>
  <div>

    <!-- just for development
    use to show viewport -->
    <v-btn
    depressed
    fixed
    absolute
    bottom
    fab 
    v-resize="onResize"
    right
    class="mb-10 pink title white--text">
    {{viewport}}
    </v-btn>
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
              :elevation="hover ? 16 : 4"
              v-resize="onResize"
              :ripple="false"
               @click="dialog =! dialog"
              class="mb-12 pa-0 w100"
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
        flat
        tile
        class="h100 w100 py-12 pa-0 ma-0">
        
            <v-row
            class="pa-0 ma-0"
            justify="center"
            align="center">

              <!-- description title-->
              <v-col  cols="12">
                <div class="text-center mb-4">
                  <span
                  class="display-1 font-weight-bold grey--text text--darken-3">
                  Noor For All</span>
                </div>
              </v-col>

              <!-- description (for loop used)-->

 
                <v-col 
                v-for="(description, index) in 3" :key="index"
                cols="12" sm="6" md="4" lg="3">
                 <v-img
                 :class="`elevation-16 pa-3 pt-0 ${animation[index]}`"
                  
                  src="../assets/illus/doodles-school-0.jpg"
                  >
                  <v-card 
                  tile
                  class="elevation-8 orange lighten-2  op95 h80 ma-5 mt-10 float-down-fast pa-0 d-flex">
                
                    <v-card 
                    tile
                    class="h100 w100 ma-5 op100 float-up-fast elevation-16">

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
      class="orange lighten-3 py-8" 
      cols="12">
      <div
      class="text-center mb-8">
        <span
        class="display-1 font-weight-bold grey--text text--darken-3">
        Our Medals</span>
      </div>
      <v-row
      justify="center"
      align="center"
      >
        <v-col
        cols="6" md="4" lg="3" xl="2"
        v-for="(medal, index) in 6" :key="index"
        >
        
          <!-- medal -->
          <div
          class="d-flex justify-center">
            <v-icon size="100">
              mdi-medal
            </v-icon>
          </div>

          <!-- title -->
          <div
          class="d-flex justify-center">
            Title
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
        v-resize="mapSize"
        v-show="fopsHorizon"
        color="indigo darken-2"
        flat
        height="80"
        >
          <div
          class="w100 d-flex justify-center">
            <div
            class="w40 d-flex mx-5 justify-space-around">

              <v-btn
              height="60"
              v-for="(fop, index) in fops" :key="index"
              @click="sheet = !sheet"
              text
              large>
              <div
              class="h100 w100">

                <!-- fop icon -->
                <div
                class="d-block text-center mb-2">
                  <v-icon
                  size="30">
                  {{fop.icon}}</v-icon>
                </div>
                
                <!-- fob title -->
                <div
                class="d-block text-center">
                  <span>{{fop.title}}</span>
                </div>

              </div>
              </v-btn>
            </div>
          </div>
        </v-app-bar>  



        <!-- Map -->
            <v-card
            :height="mapH"
            class="d-flex justify-center ma-0 pa-0 h100"
            tile>
              <v-row
              v-resize="mobile"
              class="ma-0 pa-0 h100 w100"
              justify="center"
              align="stretch">
                <v-col
                :cols="mapBP"
                class="ma-0 pa-0">
                  <v-btn
                  v-resize="mobile"
                  absolute
                  bottom 
                  flat
                  :ripple="false"
                  tile
                  color="indigo darken-3"
                  >
                    {{viewport}}
                  </v-btn>
                  <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3443.57502456997!2d48.28267815106922!3d30.33460371167148!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3fc44f12eb39a3c7%3A0xc4ec16f6be22c4da!2sNoor%20Arvand%20Educational%20institution!5e0!3m2!1sen!2s!4v1578324126941!5m2!1sen!2s"
                  class=" w100 h100"   
                  >
                  </iframe>
                </v-col>

                <!-- side fops -->
                <v-col 
                v-show="!fopsHorizon"
                cols="3"
                class="pa-0 ma-0 ">
                  <div
                  class="h100 indigo darken-4">
                    <v-row
                    class="ma-0 pa-0 h100 w100"
                    justify="center"
                    align="center">
                      <v-col
                      v-for="(fop, index) in fops" :key="index"
                      cols="12"
                      class="">
                      <v-btn
                      class="d-block"
                      height="60"
                      
                      @click="sheet = !sheet"
                      text
                      large>
                      <div
                      class="h100 w100" >

                        <!-- fop icon -->
                        <div
                        class="d-block text-center mb-2">
                          <v-icon
                          size="30">
                          {{fop.icon}}</v-icon>
                        </div>
                        
                        <!-- fob title -->
                        <div
                        class="d-block d-flex justify-center">
                          <span>{{fop.title}}</span>
                        </div>

                      </div>
                      </v-btn>
                      </v-col>
                    </v-row>
                  </div>
                </v-col>
              </v-row>
            </v-card>  

  


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
        v-model="dialog"
        fullscreen
        class="pa-0 ma-0 white"
      >

      <v-sheet class="py-10 d-flex justify-end" >

        <v-btn
          class="my-n6 mx-n3"
          fab
          absolute
          depressed
          color="pink"
          @click="dialog = !dialog"
        ><v-icon color="white">mdi-close</v-icon></v-btn>


        <component :is="c"></component>


      </v-sheet>

        
   
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
          color="pink"
          @click="sheet = !sheet"
        ><v-icon color="white">mdi-close</v-icon></v-btn>
      </v-sheet>
    </v-bottom-sheet>

    

  </v-container>
  </div>
</template>

<script>

import Archive from '../components/Archive'
import Konkur from '../components/Konkur'
import Advicer from '../components/Advicer'
import Classes from '../components/Classes'
import Teachers from '../components/Teachers'
import Exam from '../components/Exam'
import Resize from '../mixins/resize'

export default {
  name: 'home',

  components:{
    Archive,
    Konkur,
    Advicer,
    Classes,
    Teachers,
    Exam
  },
  data: () =>({   
    //data
    c : Exam,
    dialog: false,
    sheet: false,
    parallaxH:0,
    dialogH:0,
    cardH:0,
    cardW:0,
    viewport:'',
    fopsHorizon:true,
    mapH:400,
    sections:[
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
      {title:'header',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description'},
    ],
    animation:[
      'float-up-fast',
      'float-down-fast',
      'float-up-fast'
    ],
    fops:[
      {title:'CEO',icon:'mdi-glasses'},
      {title:'Contact',icon:'mdi-phone-classic'},
      {title:'FAQ',icon:'mdi-frequently-asked-questions'},
      {title:'Comment',icon:'mdi-comment-text-outline'},
    ],      
    icons: [
        'mdi-google-plus',
        'mdi-telegram',
        'mdi-instagram',
      ],
  }),
    mounted () {
      this.onResize();
      this.mapSize();
      this.mobile();
    },
    //use mixins here
    methods: {
      mobile(){
        if(this.viewport == 'xs'){
          this.fopsHorizon = false;
          this.mapBP = 9;
          this.mapH = 500;
        }
        else{
          this.fopsHorizon = true;
          this.mapBP = 12;
          this.mapH = 400
        }
      },

      dialogH(){
        this.dialogH = window.innerHeight;
      }
  },
  mixins:[Resize]
}
</script>
<style scoped>
.dialog{
  height: 90vh;
  min-height: 600px;
  
}

</style>

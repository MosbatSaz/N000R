<template>
  <div>

    <!-- just for development
    use to show viewport -->
    <!-- <v-btn
    depressed
    fixed
    absolute
    bottom
    fab 
    v-resize="onResize"
    right
    class="mb-10 pink title white--text">
    {{viewport}}
    </v-btn> -->
<!-- place home page in a grid system -->
    <v-container  fluid fill-height class="white pa-0"> 
    <v-row     
      class="ma-0"
      justify="space-between back"
    >



      <!-- hero image -->

        <!-- hero image -->
      <v-col 
      cols="12"
      class="ma-0 pa-0">
           <v-row
            align="center"
            justify="center"
            class="h100 w100 pa-0 ma-0 hero"
          >
            <v-card
            flat
            tile
            :height="heroH"
            
            class="w100 hero">

              <!-- display on -->

                <!-- lg and xl -->




                <v-img
                src="../assets/Hero.svg"
                class="pa-0 ma-0 h100 w100">
                  <v-img
                  src="../assets/Hero-quote.svg"
                  class="pa-0 ma-0 h100 w100 float-illus">
                  </v-img>

                </v-img>

            
                
         

             </v-card>  
          </v-row>
      </v-col>






    
      <!-- section cards use for loop-->
      
      <v-col
      cols="12"
      class="ma-0 pa-1 pt-2 back ">
      <v-row     
      :class="`ma-0 pa-0 ${margin}`"
      justify="space-between back"
       >
      <v-col
      v-for="(section, index) in sections" :key="index"
      cols="6" sm="6" md="4" lg="2"
      class="ma-0 pa-1 pt-2 back">
      <router-link   :to='section.route'>
        <v-hover>
          <template v-slot="{ hover }">
            <v-card
              :elevation="hover ? 16 : 4"
              v-resize="mobile"
              :height="sectionH"
              :ripple="false"
               @click="dialog =! dialog"
              class=" pa-0 w100"
            >
              <div
              class="d-flex justify-center h100 w100">
                
                  <v-row
                  justify="center"
                  align="center"
                  class="ma-0 pa-0">
                    <v-col
                    cols="12"
                    class="pa-0 ma-0">
                      <div 
                      class="text-center font-weight-black pa-0">
                        <span >{{section.title}}</span>
                      </div>
                    </v-col>
                    <v-col
                    cols="12"
                    class="ma-0 pa-0">

                    <!-- illus -->
                      <div
                      class="d-flex justify-center pa-0 ma-0">
                        <v-avatar
                        :size="illusH"
                        tile>

                          <v-img v-show="index == 0" src="../assets/archive.png"></v-img>
                          <v-img v-show="index == 1" src="../assets/advisor.png"></v-img>
                          <v-img v-show="index == 2" src="../assets/exam.png"></v-img>
                          <v-img v-show="index == 3" src="../assets/konkur-0.png"></v-img>
                          <v-img v-show="index == 4" src="../assets/classes.png"></v-img>
                          <v-img v-show="index == 5" src="../assets/teacher.png"></v-img>
                            
                        </v-avatar>
                      </div>
                    </v-col>
                  </v-row>
               
              </div>
            </v-card>
          </template>
         </v-hover>
        </router-link>
      </v-col>
      </v-row>
      </v-col>


      <!-- News -->
      <v-col 
      cols="12"
      class="pa-0 ma-0 mt-12 back" 
      >
        <v-card
        flat
        tile
        class="h100 w100 py-12 pa-0 back">
     
        
            <v-row
            class="pa-0 ma-0 back"
            justify="center"
            align="center">

              <!-- news title-->
              <v-col  cols="12">
                <div class="text-center mb-4">
                  <span
                  class="display-1 font-weight-bold grey--text text--darken-3">
                  News</span>
                </div>
              </v-col>

              <!-- news (for loop used)-->


              <v-col
              cols="12"
              v-for="i in 3" :key="i">
               <v-card
                max-width="800"
                class="mx-auto elevation-16"
                
                >
                <v-list-item>
                <v-avatar class="mr-3">
                <v-img src="../assets/noor-logo-layer.png"></v-img>
                </v-avatar>
                <v-list-item-content>
                <v-list-item-title class="headline">Our Changing Planet</v-list-item-title>
                <v-list-item-subtitle>by Noor</v-list-item-subtitle>
                </v-list-item-content>
                </v-list-item>

                <v-img
                src="../assets/illus/hero full.png"
                height="194"
                ></v-img>

                <v-card-text>
                Visit ten places on our planet that are undergoing the biggest changes today.
                </v-card-text>


                <v-expansion-panels
                :flat="true"
                :hover="true"

                >
                <v-expansion-panel
                class=""
                >
                <v-expansion-panel-header
                class="headline"><span><v-icon class="mr-2" color="indigo">mdi-more</v-icon>More</span></v-expansion-panel-header>
                <v-expansion-panel-content
                >
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                </v-expansion-panel-content>
                </v-expansion-panel>
                </v-expansion-panels>
                </v-card>

              </v-col>

            </v-row>
        
        </v-card>
      </v-col>


      <!-- Description -->
      <v-col 
      cols="12"
      class="pa-0 ma-0" 
      >
        <v-card
        flat
        tile
        class="h100 w100 py-12 pa-0 ma-0 section">
        
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
                v-for="(description, index) in descriptions" :key="index"
                cols="12" sm="6" md="4" lg="3"
                >
                 <v-img
                 :class="`elevation-16 pa-3 pt-0 ${animation[index]}`"
                  
                  src="../assets/illus/doodles-school-0.jpg"
                  >
                  <v-card 
                  tile
                  class="elevation-8 orange lighten-5  op95  ma-5 mt-10 float-down-fast pa-0 d-flex">
                
                    <v-card 
                    tile
                    class=" ma-5 op100 float-up-fast elevation-16">

                    <!-- icon -->
                      <div
                      class="d-flex justify-center my-5">
                       <v-avatar
                       tile
                        size="100">
                          <v-img
                              v-show="index == 0"
                              src="../assets/Teacher-1.png"
                              alt="John"
                          >
                          </v-img>
                           <v-img
                              v-show="index == 1"
                              src="../assets/parents.png"
                              alt="John"
                          >
                          </v-img>
                           <v-img
                              v-show="index == 2"
                              src="../assets/Organ.png"
                              alt="John"
                          >
                          </v-img>
                        </v-avatar>
                      </div>

                    <!-- header -->
                      <div
                      class="d-flex justify-center display-1 mb-5">
                        {{description.title}}
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
      class="medal py-8" 
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
        <div
        v-resize="mapSize"
        v-show="fopsHorizon"
        color=""
        height="80"
        >
        <v-img
           height="80"
           class="h100 pt-2"
           src="../assets/illus/doodle-footer.png">
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
              <router-link class="white--text" :to="fop.route">
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
              </router-link>
              </v-btn>
            </div>
          </div>
        </v-img>
        </div>  



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
                  flat
                  hover
                  height="100"
                  width="100"
                  :ripple="false"
                  tile
                  color=" transparent elevation-0 op80 ml-3 mt-12"
                  >
                  <div
                  class="  pa-0 mt-5">
                  <v-card
                  hover
                  class=" ml-6 pa-0 mt-12">
                  <div
                  class="ma-0 pa-0  pa-3 indigo darken-4">
                  <v-avatar
                    tile
                    falt
                    size="100"
                    class="elevation-0 d-block"
                  >
                    <img src="../assets/illus/map.png" alt="map">
                  </v-avatar>
                  <span class="body-2">Noor Arvand</span>
                  </div>
                  </v-card>
                  </div>
                  </v-btn>
                  <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3443.57502456997!2d48.28267815106922!3d30.33460371167148!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3fc44f12eb39a3c7%3A0xc4ec16f6be22c4da!2sNoor%20Arvand%20Educational%20institution!5e0!3m2!1sen!2s!4v1578324126941!5m2!1sen!2s"
                  class=" w100 h100 orange lighten-5"   
                  color=""
                  >
                  </iframe>
                </v-col>

                <!-- side fops -->
                <v-col 
                v-show="!fopsHorizon"
                cols="3"
                class="pa-0 ma-0 w100 h100">
                <v-img
                :height="mapH"
                class="h100"
                src="../assets/illus/doodle-footer-v.png">
                <div
                  class="h100 w100">
                    <v-row
                    class="ma-0 pa-0 h100 w100"
                    justify="center"
                    align="center">
                      <v-col
                      v-for="(fop, index) in fops" :key="index"
                      cols="12"
                      class="w100 d-flex justify-center">
                      <router-link class="white--text" :to="fop.route">
                        <v-btn
                          height="60"
                          @click="sheet = !sheet"
                          text
                          class="pa-0 ma-0"
                          large>
                          <div
                          class="h100 w100 ma-0 pa-0">

                            <!-- fop icon -->
                            <div
                            class="d-block text-center ma-0 pa-0 mb-2 ">
                              <v-icon
                              size="30">
                              {{fop.icon}}</v-icon>
                            </div>
                            
                            <!-- fob title -->
                            <div
                            class="d-block text-center ma-0 pa-0">
                              <span>{{fop.title}}</span>
                            </div>

                          </div>
                        </v-btn>
                      </router-link>
                      </v-col>
                    </v-row>
                  </div>
                </v-img>
                </v-col>
              </v-row>
            </v-card>  

  

          <v-card
          tile
          height=""
          >
          <div
            
            class="indigo  darken-4 w100 h100 white--text text-center"
          >
           <v-img
           height="150"
           class="h100 py-5"
           src="../assets/illus/doodle-footer.png">
             
                <v-btn
                  v-for="icon in icons"
                  :key="icon"
                  class="mx-4 white--text"
                  icon
                  large
                >
                  <v-icon size="36">{{ icon }}</v-icon>
                </v-btn>
           

              <v-divider class="my-2"></v-divider>

              
                <v-row
                class="mt-n3"
                justify="center"
                align="center"
                >
                  <v-col
                  cols="12">
                    <v-avatar
                    tile
                    size="50"
                    class="mb-n6"
                    >
                      <v-img
                      src="../assets/MosbatSaz +saz-overlay-11.png">
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
   
          </v-img>
          </div>
          </v-card>

        </v-card>
      </v-col>
              

    </v-row>




    
    <!-- Dialog -->
 
      <v-dialog
        v-model="dialog"
        fullscreen
        class="pa-0 ma-0 white"
      >

      <v-sheet
      class="py-10 d-flex justify-end" >

        <v-btn
          class="my-n6 mx-n3 hidden-xs-only"
          fab
          fixed
          absolute
          depressed
          color="pink"
          @click="dialog = !dialog"
        ><v-icon color="white">mdi-close</v-icon></v-btn>

        <v-btn
          class="my-10 mx-n3 hidden-sm-and-up"
          fab
          fixed
          absolute
          bottom
          depressed
          color="pink"
          @click="dialog = !dialog"
        ><v-icon color="white">mdi-close</v-icon></v-btn>
         
        <router-view></router-view>
        
        <!-- <component :is="c"></component> -->


      </v-sheet>

        
   
      </v-dialog>

      <!-- Bottom sheet -->

      <v-bottom-sheet 
      v-model="sheet" 
      :inset="false" 
      :hide-overlay="hideOverlay"
      >
      <v-sheet class="d-flex justify-center" height="500">
        <v-btn
          class="my-6 hidden-xs-only"
          depressed
          absolute
          fab
          color="pink"
          @click="sheet = !sheet"
        ><v-icon color="white">mdi-close</v-icon></v-btn>
        <v-btn
          class="mb-12 hidden-sm-and-up"
          depressed
          absolute
          bottom
          fab
          color="pink"
          @click="sheet = !sheet"
        ><v-icon color="white">mdi-close</v-icon></v-btn>

        <router-view></router-view>

      </v-sheet>
    </v-bottom-sheet>

    

  </v-container>
  </div>
</template>

<script>

// import Archive from '../components/Archive'
// import Konkur from '../components/Konkur'
// import Advicer from '../components/Advicer'
// import Classes from '../components/Classes'
// import Teachers from '../components/Teachers'
// import Exam from '../components/Exam'
import Resize from '../mixins/resize'

export default {
  name: 'home',

  // components:{
  //   Archive,
  //   Konkur,
  //   Advicer,
  //   Classes,
  //   Teachers,
  //   Exam
  // },
  data: () =>({   
    //data
    // c : Classes,
    dialog: false,
    sheet: false,
    heroH:0,
    sectionH:0,
    viewport:'',
    fopsHorizon:true,
    mapH:400,
    illusH:50,
    margin:'',
    sections:[
      {title:'Archive',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description', route:'/Archive'},
      {title:'Advicor',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description', route:'/Advicer'},
      {title:'Exam',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description', route:'/Exam'},
      {title:'Konkur',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description', route:'/Konkur'},
      {title:'Classes',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description', route:'/Classes'},
      {title:'Teachers',img:'../assets/illus/undraw_Graduation_ktn0 (1).png', description:'this is a description', route:'/Teachers'},
    ],
    descriptions:[
      {title:'Teachers',img:'../assets/Teacher-1.png',color:'orange'},
      {title:'Parents',img:'../assets/parents.png',color:'indigo'},
      {title:'Organizition',img:'../assets/Organ.png',color:'pink'},
    ],
    animation:[
      'float-up-fast',
      'float-down-fast',
      'float-up-fast'
    ],
    fops:[
      {title:'CEO',icon:'mdi-glasses',route:'/Ceo'},
      {title:'Contact',icon:'mdi-phone-classic',route:'/Contact'},
      {title:'FAQ',icon:'mdi-frequently-asked-questions',route:'/Faq'},
      {title:'Comment',icon:'mdi-comment-text-outline',route:'/Comment'},
    ],      
    icons: [
        'mdi-google-plus',
        'mdi-telegram',
        'mdi-instagram',
      ],
  }),
    mounted () {
      this.onResize(); // this function is mixin thats indicate the viewport
      this.mobile();  // this function makes the page responsive (horizontally)
    },
    //use mixins here
    methods: {
      mobile(){
        if(this.viewport == 'xs'){ //xs
          this.heroH = (window.innerHeight)*50/100
          this.sectionH = (window.innerHeight)*15/100
          this.fopsHorizon = false;
          this.mapBP = 9;
          this.mapH = 500;
          this.illusH = 60;
          this.margin ='mx-0';
        }
        else if(this.viewport == 'sm'){ //sm
          this.heroH = (window.innerHeight)*40/100
          this.sectionH = (window.innerHeight)*18/100
          this.fopsHorizon = true;
          this.mapBP = 12;
          this.mapH = 400;
          this.illusH = 70;
          this.margin ='mx-4';
        }
        else if(this.viewport == 'md'){ //md
          this.heroH = (window.innerHeight)*55/100
          this.sectionH = (window.innerHeight)*20/100
          this.fopsHorizon = true;
          this.mapBP = 12;
          this.mapH = 400;
          this.illusH = 90;
          this.margin ='mx-6';
        }
        else{ //lg and xl
          this.heroH = (window.innerHeight)*70/100
          this.sectionH = (window.innerHeight)*25/100
          this.fopsHorizon = true;
          this.mapBP = 12;
          this.mapH = 400;
          this.illusH = 110;
          this.margin ='mx-12';
        }

      },
  },
  mixins:[Resize] // viewport indicator mixin
}
</script>
<style scoped>

.hero{
  background-image: linear-gradient(to bottom,white, #f2f1f0);
}

.section{
  background-image: linear-gradient(to bottom,#f2f1f0, #fff3e0);
}

.medal{
  background-image: linear-gradient(to bottom,#fff3e0, #fcdca8);
}

</style>
fff3e0
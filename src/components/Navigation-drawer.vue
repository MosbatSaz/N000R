<template >
<div v-resize="onResize">
  
 <!-- Toolbar -->     
    <!-- <v-app-bar
    v-resize="mobile"
    app 
    flat
    class=" red pa-0 ma-0 w100" 
    :height="navH"> -->
    
    <!-- LOGO -->

     <v-btn
          v-resize="mobile"
          class="mt-8"
          flat
          text
          disabled
          fixed
          absolute
          top
          left
          fab
          :height="navH"
          :width ="navH">
            <v-avatar
            :size="logoH">
            <v-img
                src="../assets/noor-logo-layer.png"
                alt="John"
            >
            </v-img>
          </v-avatar>
          </v-btn>


        <!-- use in dev mode -->

         <v-btn
         v-show="true"
          depressed
          fixed
          absolute
          bottom
          left
          fab 
          right
          @click="switching()"
          class="mb-10 pink title white--text">
          {{viewport}}
          </v-btn>


      <!-- TEST  use this testing btn to toggle navigation drawer statement -->
      <v-btn  fixed icon height="80" width="80" class="pink white--text textFade" @click="switching()"> Toggle </v-btn>

    <v-hover>
        <template v-slot="{ hover }">
          <v-fab-transition>
          <v-btn
          v-resize="mobile"
          v-show="show"
          class="mt-10"
          :elevation="hover ? 12 : 4"
          flat
          fixed
          absolute
          top
          right
          fab
          @click="toggledrawer()"
          :height="navH"
          :width ="navH">
          <v-avatar
          class="elevation-24"
            :size="navH">

            <!-- profile -->
            <v-img
            v-if="isSwitched == 1"
            src="../assets/me.png"
            alt="profile" 
            ></v-img>

            <!-- sign up / sign in -->
            <v-icon
            v-else
            :size="fingerH"
            color="indigo darken-4"
            >
            mdi-fingerprint
            </v-icon>

          </v-avatar>
          </v-btn>
          </v-fab-transition>
        </template>
    </v-hover> 
  

   
  <!-- </v-app-bar> -->


  <!-- Navigation drawer -->
  <v-navigation-drawer 
  
  @drag="checkToggle()"
  floating
  width="350" 
  class="op90" 
  color="indigo darken-3 black--text" 
  app   
  right
  disable-resize-watcher 
  v-model="toggle">
  
      <div
      class="d-flex justify-center">
        <v-btn
        @click="toggledrawer()"
        flat
        class="indigo darken-3 pa-0 ma-0 right"
        text
        icon
        large
        >
          <v-icon
          color="white"
          >
            mdi-close
          </v-icon>
        </v-btn>
      </div>  

        <!-- 
        +this is dynamic component which used to display
          userpanel
          sign-in &
          sign-up
          in navigation drawer

          *the c is parameter to switch state of drawer
          *the @toggle is function emitted from both 
            SignIn and SignUp components to switch between
            these components 

          *$event is a number passed through the ToggleTo 
            function and tell the javascript to switch to 
            which state. 
            ($event == 0) => ToggleTo SignIn 
            ($event =! 0) => ToggleTo SignUp //($event == 1)

          *keep alive used to pin data in each state even
          if the drawer being closed  
         -->
        <component
        class="ma-0 pa-0" 
        :is="c"
        @Toggle="ToggleTo($event)"
        ></component>
 


 </v-navigation-drawer>

 </div>
</template>

<script>
import SignIn from '../components/Sign-in'
import SignUp from '../components/Sign-up'
import UserPanel from '../views/User-Panel'
import Resize from '../mixins/resize'
export default {

  name: 'Home-page',

  components:{
    SignIn,
    SignUp,
    UserPanel
  },

  data: () => ({
    c: SignUp,
    isSwitched: false,
    show: true,
    toggle: false,
    bn:true,
    viewport:'',
    navH:100,
    logoH:120,
    fingerH:80,
  }),

  //use updated lifecycle hook to sync sign-btn (on the top right hand side)
  //with the show/hide state of drawer, notice if you dont use updated the btn will
  // desapear as you drag to close the drawer in the mobile viewport
  updated(){
    this.checkToggle();
    this.onResize(); // this function is mixin thats indicate the viewport
    this.mobile();  // this function makes the page responsive (horizontally)
  },

  methods:{
    
    //this method use make the drawer vertically responsive
    mobile(){
    if(this.viewport == 'xs'){ //xs
      this.navH = 60;
      this.logoH = 72;
      this.fingerH = 48
    }
    else{ //lg and xl
      this.navH = 100;
      this.logoH = 120;
      this.fingerH = 80;
    }

    },

    //these methods use to control the show/hide of drawer 
    //and the activater btn 
    toggledrawer(){
      this.toggle =! this.toggle 
      this.show =! this.show
    },
    checkToggle(){
      (this.toggle == false) ? this.show = true : ''
    },


    //these methods use to change the component that injected in
    //in the drawer , and also state of the btn  Userpanel or sign-in sign-up
    //the ToggleTo() function controled by fucntion emitted form sign-in sign-up/
    //components
    ToggleTo(param){
     (param == 0) ? this.c = SignIn : this.c = SignUp
    },
    switching(){
     if (this.c == UserPanel){
        this.isSwitched = false;
        this.c = SignUp;
     } 
     else{
        this.isSwitched = true;
        this.c = UserPanel;
     } 

    //create a new method here

    },
    

  },
  mixins:[Resize] 
  
};
</script>

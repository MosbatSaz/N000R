<template>
<div>
  
 <!-- Toolbar -->     
    <v-app-bar
    app 
    flat
    class="transparent pa-0 ma-0 w100" 
    height="120">
    
    <!-- LOGO -->
    <div
    class="d-flex justify-center">

      <v-avatar
      size="120">
        <v-img
            src="../assets/noor-logo-layer.png"
            alt="John"
        >
        </v-img>
      </v-avatar>
  
    </div>


      <!-- TEST  use this testing btn to toggle navigation drawer statement -->
      <v-btn icon height="80" width="80" class="pink white--text textFade" @click="switching()"> Toggle </v-btn>


    <!-- Spacer -->
    <v-spacer></v-spacer>

    <v-hover>
        <template v-slot="{ hover }">
          <v-fab-transition>
          <v-btn
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
          height="100">
          <v-avatar
          class="elevation-24"
            size="100">

            <!-- profile -->
            <v-img
            v-if="isSwitched == 1"
            src="../assets/me.png"
            alt="profile" 
            ></v-img>

            <!-- sign up / sign in -->
            <v-icon
            v-else
            size="80"
            color="indigo darken-4"
            >
            mdi-fingerprint
            </v-icon>

          </v-avatar>
          </v-btn>
          </v-fab-transition>
        </template>
    </v-hover>  

   
  </v-app-bar>


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
        absolute
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
import UserPanel from '../components/User-panel'
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
    s:'hi'
  }),

  //use updated lifecycle hook to sync sign-btn (on the top right hand side)
  //with the show/hide state of drawer, notice if you dont use updated the btn will
  // desapear as you drag to close the drawer in the mobile viewport
  updated(){
    this.checkToggle();
  },

  methods:{

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

  }
};
</script>

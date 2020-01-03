<template>
<div>
  
 <!-- Toolbar -->     
    <v-app-bar
    class="pa-0 ma-0" 
    app
    flat
    color=""
    light
    height="60">
    
    <!-- LOGO -->
    <v-avatar
    size="60">
    <img
        src="../assets/noor logo.png"
        alt="John"
    >
    </v-avatar> 

    <!-- Spacer -->
    <v-spacer></v-spacer>

    <!-- Sign in Button -->
    <!-- <v-btn
      outlined
      x-large
      color="blue darken-4"
      @click="toggle =! toggle"        
    >
      <span class=" mr-2">Sign in</span>
      <v-icon c x-large>mdi-account</v-icon>
    </v-btn> -->
    <v-hover>
      <template v-slot="{ hover }">
        <v-fab-transition>
        <v-btn
        v-show="show"
        class="mt-12"
        :elevation="hover ? 16 : 8"
        flat
        fab
        height="80">
        <v-avatar
        
        @click="toggledrawer()"
        class="elevation-24"
          size="80">
          <img
              src="../assets/me.png"
              alt="John"
          >
        </v-avatar>
        </v-btn>
        </v-fab-transition>
      </template>
    </v-hover>  
  </v-app-bar>

  <!-- Navigation drawer -->
  <v-navigation-drawer 
  floating
  width="350" 
  class="op90" 
  color="blue darken-4 black--text" 
  app  
  right
  disable-resize-watcher 
  v-model="toggle">
  
      <div
      class="d-flex justify-center">
         <v-btn
        @click="toggledrawer()"
        flat
        class="blue darken-4 pa-0 ma-0 right"
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

 
        <component class="  ma-0 pa-0" :is="c"></component>


 </v-navigation-drawer>

 </div>
</template>

<script>
import SignIn from '../components/Sign-in'
import SignUp from '../components/Sign-up'
import UserPanel from '../components/User-Panel'
export default {
  name: 'Home-page',
  components:{
    SignIn,
    SignUp,
    UserPanel
    
  },
  data: () => ({
    c: UserPanel,
    show: true,
    toggle: false,
    bn:true,
  }),
  methods:{
    toggledrawer(){
      this.toggle = !this.toggle;
      this.show = !this.show;
    }
  }
};
</script>

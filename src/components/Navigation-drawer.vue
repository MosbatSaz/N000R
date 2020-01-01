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
    <v-btn
      outlined
      x-large
      color="blue darken-4"
      @click="toggle =! toggle"        
    >
      <span class=" mr-2">Sign in</span>
      <v-icon c x-large>mdi-account</v-icon>
    </v-btn>

  </v-app-bar>

  <!-- Navigation drawer -->
  <v-navigation-drawer 
  width="500" 
  class="op90" 
  color="blue darken-4" 
  app  
  right
  disable-resize-watcher 
  v-model="toggle">
  
      <div
      class="d-flex justify-center">
         <v-btn
        @click="toggle =! toggle"
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

      <!-- <div
      class="d-flex justify-center">
         <v-btn
        @click="toggle =! toggle"
        flat
        class="blue darken-4 pa-0 ma-0 hidden-sm-and-up right"
        text
        icon
        large
        absolute
        bottom
        height="50"
        width="50"
        >
          <v-icon
          x-large
          color="white"
          >
            mdi-close
          </v-icon>
        </v-btn>
      </div>  -->
  




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
    c: SignIn,
    toggle: false,
    bn:true,
  }),
};
</script>

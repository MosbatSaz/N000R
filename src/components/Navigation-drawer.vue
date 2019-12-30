<template>
<div>
  
 <!-- Toolbar -->     
    <v-app-bar
    class="pa-0 ma-0 " 
    app
    color=""
    light
    height="60">
    
    <!-- LOGO -->
    <v-icon id="op100" x-large color="black">mdi-home</v-icon>

    <!-- Spacer -->
    <v-spacer></v-spacer>

    <!-- Sign in Button -->
    <v-btn
      text
      x-large
      color="blue darken-4"
      @click="toggle =! toggle"        
    >
      <span class=" mr-2">Sign in</span>
      <v-icon c x-large>mdi-account</v-icon>
    </v-btn>

  </v-app-bar>

  <!-- Navigation drawer -->
  <v-navigation-drawer width="500" class="op90" color="teal darken-1" app right v-model="toggle">
    <v-app-bar 
    class="teal darken-1 pa-0 ma-0"
    height="40"
    flat>
         <v-btn
        @click="toggle =! toggle"
        large
        tile
        color="white"
        outlined
        class="teal darken-1 pa-0 ma-0 w100"
        height="40"
        >
          <v-icon>
            mdi-close
          </v-icon>
        </v-btn>
    </v-app-bar>


        <component class=" h100 w100 ma-0 pa-0" :is="c"></component>




 </v-navigation-drawer>

 </div>
</template>

<script>
import SignIn from '../components/Sign-in'
import SignUp from '../components/Sign-up'
export default {
  name: 'Home-page',
  components:{
    SignIn,
    SignUp
    
  },
  data: () => ({
    c: SignUp,
    toggle: false,
  }),
};
</script>

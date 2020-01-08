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

    <!-- Spacer -->
    <v-spacer></v-spacer>

    <v-hover>
        <template v-slot="{ hover }">
          <v-fab-transition>
          <v-btn
          id="#scrolling-techniques-7"
          v-show="show"
          class="mt-8"
          :elevation="hover ? 12 : 4"
          flat
          fixed
          absolute
          top
          right
          fab
          height="100">
          <v-avatar
          @click="toggledrawer()"
          class="elevation-24"
            size="100">
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

 
        <component class="  ma-0 pa-0" :is="c"></component>


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
    c: SignIn,
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

<template>
  <v-app dark>

    <navi></navi>

    <v-content class="pa-0">
      <router-view></router-view>
    </v-content>
                
  </v-app>
</template>

<script>
import Navi from './components/Navigation-drawer'
export default {
  name: 'App',
  components:{
    'navi':Navi
  },
  data: () => ({

  }),
};

</script>
<style>

/* use sass in this section to make everything smarter */

/* opacity */
@import url('https://fonts.googleapis.com/css?family=Lexend+Deca&display=swap');
/* font */
.v-application {
   /* font-family: 'Lexend Deca', sans-serif; */
   font-family:"Arabic Typesetting", serif;
 }


.op100{opacity: 1 !important}
.op95{opacity: 0.95}
.op80{opacity: 0.8}
.op70{opacity: 0.7}
.op60{opacity: 0.6}
.op50{opacity: 0.5}
.op40{opacity: 0.4}
.op30{opacity: 0.3}
.op20{opacity: 0.2}
.op10{opacity: 0.1}
.op0{opacity: 0}

/* height  */
.h100{height: 100%}
.minh700{min-height:700}
.h90{height: 90%}
.h80{height: 80%}
.h70{height: 70%}
.h60{height: 60%}
.h50{height: 50%}
.h40{height: 40%}
.h30{height: 30%}
.h20{height: 20%}
.h10{height: 10%}

/* width */
.w100{width: 100%}
.w90{width: 90%}
.w80{width: 80%}
.w70{width: 70%}
.w60{width: 60%}
.w50{width: 50%}
.w40{width: 40%}
.w30{width: 30%}
.w20{width: 20%}
.w10{width: 10%}

/* animation */

.float-up{ animation: float-up infinite 10s ease-in-out }
@keyframes float-up {
    50% { transform: translateY(-5px) }
}

.float-down{ animation: float-down infinite 10s ease-in-out }
@keyframes float-down {
    50% { transform: translateY(5px) }
}

.float-up-fast{ animation: float-down-slow infinite 10s ease-in-out }
@keyframes float-down-slow {
    50% { transform: translateY(-10px) }
}

.float-down-fast{ animation: float-up-slow infinite 10s ease-in-out }
@keyframes float-up-slow {
    50% { transform: translateY(10px) }
}

</style>
<template>
<div
class="w100 h100 pa-0 ma-0 back d-flex justify-center align-center">
  <v-card
  class="h70 w90 elevation-24"
  >

  <v-carousel 
  hide-delimiter-background
  height="900"
  cycle
  show-arrows-on-hover 
  >
    <v-carousel-item

      v-for="(item,i) in 6"
      :key="i"
      src="../assets/illus/hero full.png"
      
    >

    <div class="text-center mt-12 display-3"> This Is The Noor </div>

    </v-carousel-item>
  </v-carousel>
      
  </v-card>

</div>
</template>



<script>
  export default {
    data : () => ({
      return:{
      items: [
          {
            src: '../assets/illus/hero full.png',
          },
          {
            src: '../assets/illus/hero full.png',
          },
          {
            src: '../assets/illus/hero full.png',
          },
          {
            src: '../assets/illus/hero full.png',
          },
        ],
    },
  })
  }
</script>
<style scoped>
</style>
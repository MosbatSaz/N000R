<template>
<div
class="w100 pa-0 ma-0 red ">
  <v-carousel
    cycle
    height=""
    class="w100 pa-0 h100v"
    hide-delimiter-background
    show-arrows-on-hover
  >
      
    <v-carousel-item
      v-for="(slide, i) in slides"
      :key="i"
      class="h100v"
    >
      <v-sheet
        :color="colors[i]"
        class="h100v"
      >
        <v-row
          class="fill-height pt-12"
          align="start"
          justify="center"
        >
          <div class="display-3">{{ slide }} Slide</div>
          <v-image
          src="../assets/MosbatSaz +saz-layers.png"></v-image>
        </v-row>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</div>
</template>



<script>
  export default {
    data () {
      return {
        dynamicH: 0,
        colors: [
          'indigo',
          'warning',
          'pink darken-2',
          'red lighten-1',
          'deep-purple accent-4',
        ],
        slides: [
          'First',
          'Second',
          'Third',
          'Fourth',
          'Fifth',
        ],
      }
    },
  }
</script>
<style scoped>
</style>
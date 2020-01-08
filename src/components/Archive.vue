<template>

  <v-carousel
    cycle
    height="900"
    class=" ma-0 pa-0"
    hide-delimiter-background
    show-arrows-on-hover
  >
          <div
        class="d-flex justify-center"
        absolute
        top>
          <v-btn
          @click="dialog =! dialog"
          flat
          class="blue darken-4 pa-0 ma-0 hidden-xs-only right"
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
      
    <v-carousel-item
      v-for="(slide, i) in slides"
      :key="i"
    >
      <v-sheet
        :color="colors[i]"
        class="h100"
      >
        <v-row
          class="fill-height pt-12"
          align="start"
          justify="center"
        >
          <div class="display-3">{{ slide }} Slide</div>
        </v-row>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</template>

<script>
  export default {
    data () {
      return {
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
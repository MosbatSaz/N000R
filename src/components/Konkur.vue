<template>
    <div
    class=" pa-0 ma-0">
        <div 
        class="text-center display-3">
          Header
        </div>
        <v-card
        height="400"
        class="indigo darken-3 elevation-24 mx-12 op100 my-12">
        </v-card>

        <v-row 
        class="mx-12"
        justify="center"
        align="center">
          <v-col
          class="d-flex justify-center"
          cols="12" md="4"
          v-for="(item, index) in 3" :key="index">
            <v-card
            height="200"
            class="indigo darken-3 w100 elevation-24 op100">
            </v-card>
          </v-col>
        </v-row>
    </div>
</template>

<script>

export default {
  name: 'App',
  components:{ },

  data: () => ({
      
  }),
};

</script>
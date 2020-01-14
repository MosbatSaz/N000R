<template>
    <!-- use this div as container of user panel -->
    <div
    class="pa-0 ma-0 w100 ">

      <!-- place avatar and the name below in a div to center it -->
      <div
      class="d-flex justify-center mt-12">
        <v-avatar
        class="mt-5 elevation-24"
          size="200">
          <img
              src="../assets/me.png"
              alt="John"
          >
        </v-avatar>
 
      </div> 

      <!-- user name -->
      <div
      class="d-flex justify-center my-5">
        <span
        class="headline white--text font-weight-thin">
        i V N O
        </span>
      </div> 

      <!-- block spacer -->
      <div
      class="d-flex justify-center w100 black--text">
          <v-card
          class="h100 white--text pink lighten-1"
          width="200"
          flat
          >
          <v-responsive
          :aspect-ratio="16/1">
              
          </v-responsive>
          </v-card>
      </div>

      <!-- user panle items -->
      <!--  -->
      <v-list 
      class="">
        <v-subheader></v-subheader>
        <v-list-item-group v-model="item" >
          <v-list-item
            v-for="(item, i) in items"
            :key="i"
            :class="`d-flex justify-end ${item.color}`"
            color="white"
          >
            <v-list-item-icon >
              <v-icon large v-text="item.icon"></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title class="subtitle-1	" v-text="item.text"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </div>
</template>


<script>
  export default {
    data: () => ({
      item: 1,
      items: [
        { text: 'Classes', icon: 'mdi-book-open-variant',color:'' },
        { text: 'Advicer', icon: 'mdi-voice',color:'' },
        { text: 'test Mark', icon: 'mdi-file-outline',color:'' },
        { text: 'Comments', icon: 'mdi-comment-multiple-outline',color:'' },
        { text: 'Exit', icon: 'mdi-exit-to-app',color:'pink lighten-1' },
      ],
    })
  }
</script>
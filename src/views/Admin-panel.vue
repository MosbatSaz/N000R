<template>
  <div class="back ma-0 pa-0 h100 w100">

  <!-- Content -->




  <!-- News -->

  <div v-if="news" class="back ma-0 pa-0 h100 w100">


              <!-- create a new post -->

              <!-- title -->
              <div
              class="display-1 text-center py-5">
              <span class="display-1 indigo--text">+</span> Create a New Post <span class="display-1 indigo--text">+</span>
              </div>

              <!-- posts -->
              <div class=" w100 d-flex justify-center">
                <v-card
                max-width="800"
                class="h100 w90 elevation-16 ma-2"
                
                >
                <v-list-item>
                <v-avatar class="ml-3">
                <v-img src="../assets/noor-logo-layer.png"></v-img>
                </v-avatar>
                <v-list-item-content>
                <v-list-item-title class="headline">Our Changing Planet</v-list-item-title>
                <v-list-item-subtitle>by Noor</v-list-item-subtitle>
                </v-list-item-content>
                </v-list-item>

                <v-img
                src="../assets/illus/hero full.png"
                height="200"
                ></v-img>

                <v-card-text>
                Visit ten places on our planet that are undergoing the biggest changes today.
                </v-card-text>


                <v-expansion-panels
                :flat="true"
                :hover="true"

                >
                <v-expansion-panel
                class=""
                >
                <v-expansion-panel-header
                class="title"><span>More</span></v-expansion-panel-header>
                <v-expansion-panel-content
                >
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                </v-expansion-panel-content>
                </v-expansion-panel>
                </v-expansion-panels>
                </v-card>
                </div>


                  <!-- divider -->
                      <v-divider class="mt-12"></v-divider>





              <!-- post archive -->

              <!-- title -->
              <div
              class="display-1 text-center mb-5">
              <span class="display-4 indigo--text">.</span> Post Archive <span class="display-4  indigo--text">.</span>
              </div>

              <!-- posts -->
              <div v-for="(item, index) in 10" :key="index" class="w100 d-flex justify-center">
                <v-card
                max-width="800"
                class="h00 w90 elevation-16 ma-2 mb-4">
                
                    <v-btn
                    class="mt-3 hidden-xs-only elevation-16 float-illus"
                    fab
                    right
                    absolute
                    depressed
                    color="pink"
                    @click="remove(index)"
                    ><v-avatar size="35" tile class="">
                    <v-img src="../assets/bin.png"></v-img>
                    </v-avatar></v-btn>

                    <v-btn
                    class="mt-12 hidden-sm-and-up elevation-16 float-illus"
                    fab
                    right
                    absolute
                    depressed
                    color="pink"
                    @click="remove(index)"
                    ><v-avatar size="35" tile class="">
                    <v-img src="../assets/bin.png"></v-img>
                    </v-avatar></v-btn>


                
                <v-list-item>
                <v-avatar class="ml-3">
                <v-img src="../assets/noor-logo-layer.png"></v-img>
                </v-avatar>
                <v-list-item-content>
                <v-list-item-title class="headline">Our Changing Planet</v-list-item-title>
                <v-list-item-subtitle>by Noor</v-list-item-subtitle>
                </v-list-item-content>
                </v-list-item>

                <v-img
                src="../assets/illus/hero full.png"
                height="200"
                ></v-img>

                <v-card-text>
                Visit ten places on our planet that are undergoing the biggest changes today.
                </v-card-text>


                <v-expansion-panels
                :flat="true"
                :hover="true"

                >
                <v-expansion-panel
                class=""
                >
                <v-expansion-panel-header
                class="title"><span>More</span></v-expansion-panel-header>
                <v-expansion-panel-content
                >
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                </v-expansion-panel-content>
                </v-expansion-panel>
                </v-expansion-panels>
                </v-card>
              </div>  
  </div>




  <!-- comments -->

  <div v-else class="back ma-0 pa-0 h100 w100">
    <span class="display-1"> This is Comments</span>
  </div>



















  <!-- Navigation -->

    <v-navigation-drawer
      expand-on-hover
      height="410"
      app
      fixed
      permanent
      right
      class="hidden-xs-only nav elevation-1"
      width="200"
    >
    <div
    class="d-flex justify-end align-center">
      <span class="display-2 deep-purple--text text--darken-4 font-weight-thin">Noor</span>
      <v-avatar
      size="80"
      class="ml-2"
      >
        <img src="../assets/noor-logo-layer.png">
      </v-avatar>
    </div>

      <v-divider class="my-1"></v-divider>
      
    <div
    v-for="(btn, index) in 4" :key="index"
    class="d-flex  justify-end">      
       <v-btn
          depressed
          fab 
          :ripple="false"
          height="75"
          width="200"
          @click="btnFunction(index)"
          class=" mr-3 transparent title white--text d-flex justify-end">

          <div>
          <span v-if="index == 0" class="deep-purple--text text--darken-4">News</span>
          <span v-else-if="index == 1" class="deep-purple--text text--darken-4">Comment</span>
          <span v-else-if="index == 2" class="deep-purple--text text--darken-4">More</span>
          <span v-else class="deep-purple--text text--darken-4">Exit</span>
          <v-avatar
          size="50"
          class="ml-5"
          tile
          >


            <v-img 
            v-show="index == 0"
            src="../assets/news.png">
            </v-img>


            <v-img
            v-show="index == 1"
            src="../assets/comments.png">
            </v-img>

             <v-img
             v-show="index == 2"
            src="../assets/more.png">
            </v-img>

            <v-img
             v-show="index == 3"
            src="../assets/logout.png">
            </v-img>

          </v-avatar>
          </div>
          
        </v-btn>
    </div>


    </v-navigation-drawer>


  <v-bottom-navigation
    fixed
    bottom
    :ripple="false"
    height="70"
    class="hidden-sm-and-up"
  >
        <v-btn
          v-for="(btn, index) in 4" :key="index"
          depressed
          fab 
          height="70"
          width="70"
          class=" transparent mx-2 title white--text">
          <v-avatar
          size="50"
          tile
          @click="btnFunction(index)">

            <v-img 
            v-show="index == 0"
            src="../assets/news.png">
            </v-img>

            <v-img
            v-show="index == 1"
            src="../assets/comments.png">
            </v-img>

             <v-img
             v-show="index == 2"
            src="../assets/more.png">
            </v-img>

            <v-img
             v-show="index == 3"
            src="../assets/logout.png">
            </v-img>

          </v-avatar>
        </v-btn>

  </v-bottom-navigation>



    <v-bottom-sheet v-model="sheet" inset>
      <v-sheet class="text-center" height="100">
        <span class="display-2">Coming Soon</span>
      </v-sheet>
    </v-bottom-sheet>


    <v-dialog
      v-model="logout"
      max-width="400"
    >
      <v-card>
        <v-card-title class="headline">Do you Want to Log Out?</v-card-title>
        <div
        class="d-flex justify-center">
          <v-avatar
          size="100"
          tile>
            <v-img src="../assets/logout.png">
            </v-img>
          </v-avatar>
        </div>
        <v-card-text>
          This Means You Want to Leave Admin Panel.
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn
            color="indigo"
            text
            @click="logout()"
          >
            Disagree
          </v-btn>

          <v-btn
            color="pink"
            text
            @click="logout()"
          >
            Agree
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>

  </div>
</template>


<script>
export default {
  name:'test',

  data:() => ({
    news:true,
    sheet:false,
    logout:false,
  }),

  methods:{
    btnFunction(index){

      if(index == 0){this.news = true}
      else if(index == 1){this.news = false}
      else if(index == 2){this.sheet = true}
      else{this.logout = true}

    },
    remove(index){
      index//
    }
  }
}
</script>

<style scoped>
.nav{
  border-bottom-left-radius: 45px;
}  
</style>


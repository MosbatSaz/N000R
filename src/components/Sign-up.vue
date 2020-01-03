<template>
    
    <v-container fluid class="pa-0 ma-0 indigo lighten-1 h90">
        <v-row 
        no-gutters
        class=" ma-0 pa-0 h100"
        justify="center"
        align="start"
        >
            <!-- finger-print -->
            <v-col 
            cols="12"
            class="pa-0 ma-0 "
            >   
                <div 
                class="d-flex justify-center">
                    <!-- <v-avatar>
                       <v-file-input
                       solo 
                       class="ma-0 pa-0"
                       width="200">
                       </v-file-input>
                    </v-avatar> -->
                       
                       
                </div>
            </v-col>

            <!--input fields -->
            <v-col 
            cols="12"
            class="ma-0 pa-0 ">
                <div
                class="d-flex justify-center w100 mb-6">
                    <v-card
                    class="h100 white--text"
                    width="200"
                    flat
                    >
                    <v-responsive
                    :aspect-ratio="16/1">
                       
                    </v-responsive>
                    </v-card>
                </div>
                <div
                v-for="(i, index) in 6" :key="index"
                class="d-flex justify-center mb-6">
                <v-card
                flat
                width="300"
                height="50"
                class="">
                    <v-text-field
                    height="50"
                    solo
                    >

                    </v-text-field>
                </v-card>
                </div>
                <div
                class="d-flex justify-center ma-0  pa-0">
                    <v-card
                    flat
                    class="teal darken-1"
                    width="300"
                    height="50">
                        <v-checkbox
                        v-model="checkbox"
                        color="white"
                        label="I agree to the terms of Noor Edu"
                        ></v-checkbox>
                    </v-card>
                </div> 
                <div
                class="d-flex justify-center ma-0 mt-6 pa-0">
                    <v-btn
                    class="blue"
                    width="300"
                    height="50">
                    
                    </v-btn>
                </div> 
 
            </v-col>

            <!-- sign in btn -->
            <!-- <v-col 
            cols="12"
            class="ma-0 my-n12 pa-0 ">
   
            </v-col>   -->

            <!-- forget password -->


            <!-- sign in with google -->
 
            <!-- block spacer -->


            <!-- create a new account -->
  

                                                     
        </v-row>
    </v-container>


</template>

<script>
export default {
    
}
</script>
<style scoped>
    
</style>
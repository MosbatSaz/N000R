<template>

    <v-container fluid  min-height="800" class="pa-0 ma-0 teal darken-1 h80">
        <v-row 
        no-gutters
        class=" ma-0 pa-0 h100"
        justify="center"
        align="start"
        >
            <!-- finger-print -->
            <v-col 
            cols="12"
            class="pa-0 ma-0 mt-12"
            >   
                <div 
                class="d-flex justify-center">
                    <v-avatar
                        >
                        
                        <v-icon  
                        class="" 
                        color="white" 
                        x-large>
                        mdi-fingerprint
                        </v-icon>
                    </v-avatar>    
                </div>
            </v-col>

            <!-- block spacer -->
            <v-col 
            cols="12"
            class="ma-0 mb-4 pa-0">
                <div
                class="d-flex justify-center w100">
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
    
            </v-col>

            <!--input fields -->
            <v-col 
            cols="12"
            class="ma-0 mt-n12 pa-0 ">
                <div
                class="d-flex justify-center mb-6">
                <v-card
                flat
                width="300"
                height="50"
                class="">
                    <v-text-field
                    height="50"
                    solo>

                    </v-text-field>
                </v-card>
                </div>
                <div
                class="d-flex justify-center">
                <v-card
                flat
                width="300"
                height="50"
                class="">
                    <v-text-field
                    height="50"
                    solo>

                    </v-text-field>
                </v-card>
                </div>
            </v-col>

            <!-- sign in btn -->
            <v-col 
            cols="12"
            class="ma-0 mb-n12 mt-n9 pa-0 ">
                <div
                class="d-flex justify-center">
                    <v-btn
                    class="blue"
                    width="300"
                    height="50">
                    
                    </v-btn>
                </div>    
            </v-col>  

            <!-- forget password -->
            <v-col 
            cols="12"
            class="ma-0 mb-n10 mt-n5  pa-0" >
                <div class="text-center">
                    Forget Password?
                </div>   
            </v-col>

            <!-- sign in with google -->
            <v-col cols="12">
            <div
            class="d-flex justify-center">
                <v-card
                width="300">
                    <v-responsive
                    :aspect-ratio="16/5">
                        
                    </v-responsive>
                </v-card>
            </div>
            
                    
            </v-col>    

            <!-- block spacer -->
            <v-col 
            cols="12"
            class="ma-0 my-n8 pa-0">
                <div
                class="d-flex justify-center w100">
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
    
            </v-col>

            <!-- create a new account -->
            <v-col 
            cols="12"
            class="ma-0 my-n12 pa-0 ">
                <div
                class="d-flex justify-center">
                    <v-btn
                    class="green accent-4"
                    width="300"
                    height="50">
                    
                    </v-btn>
                </div>    
            </v-col>  

                                                     
        </v-row>
    </v-container>


</template>

<script>
export default {
    
}
</script>
<style scoped>
    
</style>
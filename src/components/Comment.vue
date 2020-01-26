<template>
    <div
    class=" rtl ma-0 pa-0 h80 w100">

     <div
        class="float-illus d-flex justify-center ma-0 my-6 pa-0">
            <v-avatar
            tile
            size="200">
                <v-img
                src="../assets/chat.png">

                </v-img>
            </v-avatar>
        </div>


        <v-textarea
        v-model="bio"
        
        color="back"
        class="mx-6"
        solo
        >
            <template v-slot:label>
                <div>
                Tell Me What You Think About  <span class="pink--text font-weight-black"> : ) </span>
                </div>
            </template>
        </v-textarea>

        
        <div
        class="d-flex justify-center ma-0 mt-0 pa-0">
            <v-text-field
            append-icon="mdi-phone"
            class="darken-3  mx-6 white--text  text-capitalize"
            width="300"
            color="deep-purple darken-3"
            solo
            placeholder="enter your number"
            >
            </v-text-field>
        </div> 

        <div
        class="d-flex justify-center ma-0 mt-0 pa-0">
            <v-btn
            class="op95 deep-purple  darken-3 elevation-16 white--text headline text-capitalize"
            width="300"

            height="50">
            Submit
            </v-btn>
        </div> 
    </div>
</template>

<script>
export default {
    data: () => ({
        bio: '',
    })
}
</script>
<template>
    <div
    class="transparent ma-0 pa-0  w100 d-flex justify-center align-center">
                <v-card
                v-resize="onResize"
                :height="(viewport == 'xs') ? 650 : 550"
                tile
                flat
                class="h100 transparent  d-flex justify-center align-center   mb-n12"
                >
                <v-img
                src=""
                class="transparent h100 d-flex justify-center align-center "
                >
                <!-- <div class="text-center mt-n12 mb-12 display-2">Faq</div> -->
                <div
                class=" w100  d-flex justify-center align-center">
                    <div
                    class="w80">
                    
                        <v-expansion-panels
                        >  
                        
                            <v-expansion-panel
                            active-class="white--text pink lighten-2 lighten elevation-24"
                            v-for=" (faq, index) in faqs "
                            :key="index"
                            class=""
                            >
                                <v-expansion-panel-header class="text-center" disable-icon-rotate expan>
                                    <span class="">{{index+1}}.{{messege}} {{faq.question}}</span> 
                                    
                                    <template v-slot:actions>
                                        <v-icon color="white">mdi-comment-question</v-icon>
                                    </template>
                                </v-expansion-panel-header>

                                <v-expansion-panel-content class="white--text">
                                    {{faq.answer}}
                                </v-expansion-panel-content>

                            </v-expansion-panel>
                        </v-expansion-panels>
                    </div > 
                </div>   



                </v-img>
                </v-card>
                
               


    </div>

</template>

<script>
import Resize from '../mixins/resize'

export default {

    data :  () => ({
            viewport:'',
            WH:800,
            faqs:[
            {
                question:'How to Noor Arvand?',
                answer:'Veniam minim aliqua ullamco irure laborum minim ea laborum adipisicing in pariatur nisi laborum id. In irure nulla nulla irure. Consequat excepteur ea anim nisi esse deserunt cillum amet sit id ipsum. Esse mollit duis adipisicing cillum.'
            },
                {
                question:'How to Noor Arvand?',
                answer:'Veniam minim aliqua ullamco irure laborum minim ea laborum adipisicing in pariatur nisi laborum id. In irure nulla nulla irure. Consequat excepteur ea anim nisi esse deserunt cillum amet sit id ipsum. Esse mollit duis adipisicing cillum.'
            },
                {
                question:'How to Noor Arvand?',
                answer:'Veniam minim aliqua ullamco irure laborum minim ea laborum adipisicing in pariatur nisi laborum id. In irure nulla nulla irure. Consequat excepteur ea anim nisi esse deserunt cillum amet sit id ipsum. Esse mollit duis adipisicing cillum.'
            },
                {
                question:'How to Noor Arvand?',
                answer:'Veniam minim aliqua ullamco irure laborum minim ea laborum adipisicing in pariatur nisi laborum id. In irure nulla nulla irure. Consequat excepteur ea anim nisi esse deserunt cillum amet sit id ipsum. Esse mollit duis adipisicing cillum.'
            },
                {
                question:'How to Noor Arvand?',
                answer:'Veniam minim aliqua ullamco irure laborum minim ea laborum adipisicing in pariatur nisi laborum id. In irure nulla nulla irure. Consequat excepteur ea anim nisi esse deserunt cillum amet sit id ipsum. Esse mollit duis adipisicing cillum.'
            },
            ],

    }),

    mixins:[Resize],

    mounted () {
      this.onResize(); // this function is mixin thats indicate the viewport
      this.getWH();
    },

    methods:{
        openDialog(index){
            this.toggle =! this.toggle;
            this.j = index;
        },
        getWH(){
            this.WH = window.innerHeight
        }
    },

}
</script>
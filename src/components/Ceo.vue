<template>
    <div
    class="transparent ma-0 pa-0 mt-12 w100 d-flex justify-center align-center">
                <v-card
                v-resize="onResize"
                :height="(viewport == 'xs') ? 650 : 550"
                
                flat
                class="transparent  mx-5 "
                >

                    <v-card
                    flat
                    
                    class="transparent op95 h100 w100 d-flex justify-center align-start">
                        <v-card
                        max-width="800"
                        shaped
                        class="w100 rtl  accent-2 lighten-1 mx-5 elevation-16"
                        
                        >
                        <v-list-item>
                        <v-avatar size="100" class="ml-3 my-3">
                        <v-img src="../assets/ceo-min.png"></v-img>
                        </v-avatar>
                        <v-list-item-content>
                        <v-list-item-title class="headline">Mis Mir Hoseini</v-list-item-title>
                        <v-list-item-subtitle>Noor CEO</v-list-item-subtitle>
                        </v-list-item-content>
                        </v-list-item>

                        <v-tabs
                        v-model="toggle"
                        vertical
                        dark
                        color="black"
                        slider-color="white"
                        background-color=" grey  "
                        
                        class="elevation-2"
                        >
                            <v-tabs-slider></v-tabs-slider>

                            <v-tab
                            width="100"
                            v-for="(tab, index) in tabs"
                            :key="index"
                            >
                            {{ tab.title }}
                            <v-icon v-if="icons">{{tab.icon}}</v-icon>
                            </v-tab>

                            <v-tab-item
                            v-for="(tab, index) in tabs"
                            :key="index"
                            >
                            <v-card
                            flat
                            tile
                            class="back"
                            >
                            <v-card-text
                            class="">
                                
                                <span class="body-1 txt black--text" v-if="index == 0">
                                    Amet exercitation magna enim laborum qui in reprehenderit cupidatat elit.
                                    Amet exercitation magna enim laborum qui in reprehenderit cupidatat elit.
                                </span>
                                <span class="ltr" v-else>
                                    <div class="my-3" v-for="(icon, index) in icons" :key="index">
                                        <v-icon size="30" class="mr-2" :color="icon.color">{{icon.icon}}</v-icon>
                                        <span class="body-1 black--text">{{icon.text}}</span> 
                                    </div>
                                </span>


                            </v-card-text>
                            </v-card>
                            </v-tab-item>
                            </v-tabs>

                        </v-card>
                    </v-card>


                   
                </v-card>

    </div>

</template>

<script>
import Resize from '../mixins/resize'
export default {
    data :  () => ({
        toggle:null,
        viewport:'',
        icons:[
        {icon:'mdi-phone',color:'green accnet-3',text:'+98 900 000 0000'},
        {icon:'mdi-gmail',color:'deep-orange accent-3',text:'G.me@gmail.com'},
        {icon:'mdi-instagram',color:'pink',text:'@insta_me'},
        {icon:'mdi-telegram',color:'indigo',text:'@ t.me'},
        ],
        tabs:[
            {title:'Me',icon:'mdi-talk',color:'purple'},
            {title:'Info',icon:'mdi-info',color:'orange lighten-3'},
        ]
    }),

    methods:{
        //
    },
    
    mixins:[Resize],

    mounted () {
      this.onResize(); // this function is mixin thats indicate the viewport
      this.getWH();
    },

}
</script>






                    
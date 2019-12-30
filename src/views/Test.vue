<template>
  <div class="test h100">
    <v-container   fluid fill-height class="blue darken-4">
      <v-row
      class="pa-0 ma-0 h100"
      justify="center"
      align="end"
      align-md="start"
      align-sm="center">

        <v-col 
        cols="2"
        v-for="(box, index) in boxs" :key="index"
        :justify-self="box.justify"
        :align-self="box.align">
          <v-row
          class="ma-0"
          justify="center"
          align="center">
            <v-cols cols="12">
              <v-card
              hover
              height="100"
              width="100"
              :class="`${box.color}`"
              >
                <v-row
                class="h100"
                justify="center"
                align="center">
                  <v-cols
                  cols="12">
                    {{index+1}}
                  </v-cols>
                </v-row>
              </v-card>
            </v-cols>
          </v-row>
        </v-col>

      </v-row>
    </v-container>
  </div>
</template>


<script>
export default {
  name:'test',
  data:() => ({
    boxs:[
      {color:'yellow',justify:'',align:''},
      {color:'white',justify:'',align:''},
      {color:'pink',justify:'',align:''},
      {color:'purple',justify:'',align:''},
      {color:'cyan',justify:'',align:''},
      {color:'teal',justify:'',align:''},
    ]
  })
}
</script>
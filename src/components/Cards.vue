<template>
  <v-card
    class="mx-auto"
    color="#26c6da"
    dark
    max-width="400"
  >
  <v-row>
      <v-card-title>
        Awesome Quotes {{ id_ +1 }} 
    </v-card-title>
    <v-spacer></v-spacer>
    <v-btn
      color="primary"
      depressed
    >
      <v-icon left @click="deletePost(id_)">{{ icons.mdiDelete }}</v-icon>
    </v-btn>
  </v-row>
    <v-card-text class="headline font-weight-bold">
      {{quotes}}
    </v-card-text>

    <v-card-actions>
      <v-list-item class="grow">
        <v-list-item-content>
          <v-list-item-title>{{author}}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-card-actions>
  </v-card>
</template>


<script>
import { mdiDelete } from '@mdi/js'
import { reactive } from '@vue/composition-api'
 
export default {
    name:'Cards',
    props:{
        id_:Number,
        quotes:String,
        author:String,
        deletePost:Function
    },

    setup(){
     const icons = reactive({
        mdiDelete,
      })

     return { icons }
    }
}
</script>

<style>

</style>
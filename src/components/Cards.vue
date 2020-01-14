<template>
    <v-card
    class="mx-auto"
    color="#26c6da"
    dark
    max-width="400"
  >
    <v-card-title>
        Awesome Quotes {{id_}} 
    </v-card-title>
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
export default {
    name:'Cards',
    props:{
        id_:String,
        quotes:String,
        author:String
    }

    // setup(props, {context} ){

    //   const deletePost = () =>{
    //     emit('deletPost', )
    //   }
    //   return { deletePost }
    // }
}
</script>

<style>

</style>
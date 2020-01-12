<template>
  <div>
    <v-card
        class="mx-auto"
        max-width="344"
    >
     <v-card-text>
      <div>quote of the Day</div>
      <p class="display-1 text--primary">
        {{quotes}}
      </p>
      <div class="text--primary">
        {{author}}
      </div>
    </v-card-text>
    <v-card-actions>
      <!-- <v-btn
        text
        color="deep-purple accent-4"
      >
        Learn More
      </v-btn> -->
     </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
    name:'Cards',
    props:{
        quotes:String,
        author:String
    }

}
</script>

<style>

</style>
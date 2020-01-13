<template>
  <div id=beauty>
    <card-form>
      <h2>Beautiful quotes</h2>
      <form>
        <legend>Wonderful quotes</legend>
        author: <input type="text" name="author">
        quote: <input type="text" name="quote">
        <input type="submit" value="submit">
      </form>
    </card-form>
     <v-container >
      <v-row >
        <v-col
          v-for='quotes in state.quotes' 
          :key='quotes.id'
          cols="6"
          md="4"
        >
          <cards 
            class="pa-2"
            :quotes="quotes.quote"
            :author="quotes.author"
         ></cards>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import { reactive } from '@vue/composition-api'
import Cards from '@/components/Cards.vue'
import CardForm from '@/components/NewQuotes.vue'

export default {
  name: 'App',

  components: {
      Cards,
      CardForm
    },
   setup(){
      const state = reactive({
        quotes:[
         {
          quote:"I am neither late nor early, I appear exactly when I mean to ",
          author:" gandalf"
         },
         {
          quote:"learning is not the craming of facts but the training of the mind to think ",
          author:" Albert Einstein"
         },
         {
          quote:"whether you think you can or you can't you are right ",
          author:"Henry Ford"
         },
         {
          quote:"It is more honourable to fail than to cheat",
          author:"Abraham lincoln"
         }
        ]
      })  
      return { state }
  }

};
</script>

<style scoped>
  /* #beauty{
    background-color:honeydew
  } */
</style>

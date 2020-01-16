<template>
  <div id=beauty>

    <!-- from for entering new quotes and their authors -->
    <div>
      <card-form
       @newQuote='newEntry($event)'>
      </card-form>
    </div>

    <!-- The card components for the existing quotes -->
    <div>
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
                :id_="quotes.id"
                :quotes="quotes.quote"
                :author="quotes.author"
            ></cards>
            </v-col>
        </v-row>
      </v-container>
    </div>

    <!-- <p>{{state.quotes.length}}</p> -->

    <pagination :items='state.quotes.length'></pagination>

  </div>
</template>

<script>
import { reactive } from '@vue/composition-api'
import Cards from '@/components/Cards.vue'
import CardForm from '@/components/NewQuotes.vue'
import Pagination from '@/components/Pagination.vue'

export default {
  name: 'App',

  components: {
      Cards,
      CardForm,
      Pagination
    },
   setup(){
      const state = reactive({
        quotes:[
         {
          quote:"I am neither late nor early, I appear exactly when I mean to ",
          author:" gandalf"
         },
        ]
      })
      
      // const pageNumber = 

      const newEntry = entry => {
        state.quotes.push(entry)
      }
      return { state, newEntry }
  }

};
</script>

<style scoped>
  #beauty{
    background-color:honeydew
  }
</style>

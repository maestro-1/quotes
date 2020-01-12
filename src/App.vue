<template>
  <div>
    <cards :quotes="state.quote"
    :author="state.author"
    ></cards>
  </div>
</template>

<script>
import { reactive } from '"@vue/composition-api";'
import Cards from '@/components/Cards.vue'

export default {
  name: 'App',

  components: {
      Cards
    },
    // data: ()=>({
    //   quote:"I am neither late nor early, I appear exactly when I mean to ",
    //   author:" gandalf"
    // }),
   setup(){
      const state = reactive({
        quotes:"I am neither late nor early, I appear exactly when I mean to ",
        author:" gandalf"
      })  
      return state
  }

};
</script>

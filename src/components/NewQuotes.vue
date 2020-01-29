<template>
  <div>
    <h2>Beautiful quotes</h2>

        <div id="forms">
         <v-text-field label="author" hide-details="auto" v-model.lazy="state.author"></v-text-field>
          <v-text-field label="quotes" v-model.lazy="state.quote"></v-text-field>
          <button type="button" class="btn btn-primary"
           @click="post()"> post </button>
         </div>

  </div>
</template>

<script>
import { reactive, ref, watch } from '@vue/composition-api'
export default {
    name:'CardForm',

    props:[],

    setup(props, {emit}){
      const state = reactive({
        author:'',
        quote:''
      })

      const submit = ref(false)

      const post = () => {
        emit('newQuote', { author:state.author, quote:state.quote})
        submit.value = !submit.value
        setTimeout(()=>{
          state.author = '',
          state.quote = ''
        }, 1000)
      }

      watch(()=>{
        submit.value = false
      })

      return  { state, post }
    }
}
</script>

<style scope>
  #forms{
    padding-left: 20%;
    padding-right: 20%
  }
</style>

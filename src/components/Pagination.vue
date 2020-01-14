<template>
  <div class="text-center">
    <v-pagination
      v-model="page"
      :length="Apage"
    ></v-pagination>
</div>
</template>

<script>
import { computed } from '@vue/composition-api'

export default {
    name:'Pagination',
    props:{
        page:Number
    },

    setup(props){

      const Apage = computed(()=> Math.floor(props.page/9) + 1)
      
      return { Apage }
     }
    }

</script>

<style>

</style>
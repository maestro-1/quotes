<template>
  <div class="text-center">

    <div v-if="Apage < 1">
      <v-pagination
       v-model="count.value"
       :length="1"
      ></v-pagination>
    </div>

    <div v-else>
     <v-pagination
      v-model="Apage"
      :length="Apage"
     ></v-pagination>
    </div>

</div>
</template>

<script>
import { computed, ref } from '@vue/composition-api'

export default {
    name:'Pagination',
    props:{
        items:Number
    },

    setup(props){
      const count = ref(1)

      const Apage = computed(()=> {
        let page = props.items

        return Math.floor(page/9) + 1
        })
      
      return { Apage, count }
     }
    }

</script>

<style>

</style>
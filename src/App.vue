<template>
  <div id="app">
    <cheader></cheader>
    
    <router-view/>
  </div>
</template>

<script>
import Cheader from "@/components/Cheader.vue"
export default {
  components:{
    Cheader
  }
}
</script>


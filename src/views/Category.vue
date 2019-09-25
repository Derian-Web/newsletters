<template>
 <div>
      <div class="container d-flex">
      <div class="row m-0 ">
        <div class="col-4" v-for="tag in Tags" :key="tag.id">
    <card :title="tag.title" :description="tag.description" :image="tag.image"></card>
        </div>
    </div>
    </div>
  
 </div>
</template>
<script>
import Card from "@/components/Card.vue"
import axios from 'axios'
export default {
  components: {
  Card
  },
  data(){
    return{
        Tags: []
    }
  },
  created(){
  this.getTags()
  },
  watch:{
    '$route.params.slug': function (newslug){
      this.getTags()
    }
  },
  methods:{
    getTags(){
      const url = `${process.env.VUE_APP_API_CLI}/tags/${this.$route.params.slug}?include=newsletters`
      axios.get(url)
      .then(response =>{
        this.Tags = response.data.newsletters
        console.log(this.Tags)

      })
      .catch(error => {
        console.log(error.response)
      })
    }
  }

}
</script>

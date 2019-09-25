<template>
  <div class="home">
    <h2 class="text-center">Real news, curated by real humans</h2>
    <div class="container d-flex">
      <div class="row m-0 ">
        <div class="col-4" v-for="tag in tags" :key="tag.id">
    <card :title="tag.title" :description="tag.description" :image="tag.image"></card>
        </div>
    </div>
    </div>
  </div>
</template>
<script>
import Cheader from "@/components/Cheader.vue"
import Card from "@/components/Card.vue"
import axios from 'axios'
export default {
  name: 'home',
  components: {
  Cheader,
  Card
  },
  data(){
    return{
      tags: {
        tags: []
      },
    }
  },
  created(){
  this.getTags()
  },
  methods:{
    getTags(){
      const url = process.env.VUE_APP_API_CLI + '/newsletters'
      axios.get(url)
      .then(response =>{
        this.tags = response.data
        console.log(this.tags)

      })
      .catch(error => {
        console.log(error.response)
      })
    }
  }

}
</script>

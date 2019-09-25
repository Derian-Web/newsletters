<template>
    <div>
    <!-- Image and text -->
<nav class="navbar navbar-light ">
  <a class="navbar-brand" id="naranja1">[ INSIDE ]</a>
  <form class="form-inline">
    <a href="" class="mr-4 Narnjaicon"><i class="fas fa-search"></i></a>
   <a href="" class="mr-4 Narnjaicon" ><i class="fas fa-user"></i></a>
    <button class="btn btn-outline-success my-2 my-sm-0 boton-color" type="submit">SPONSORSHIP</button>
  </form>
</nav>
<div class="ml-4">
    <ul class="nav nav-pills" >
  <li class="nav-item" id="color" v-for="tag in tags" :key="tag.id">
    <router-link :to="'/category/'+tag.slug" class="nav-link">
            {{ tag.name }}
          </router-link>
  </li>
  
</ul>
</div>
<hr class="mt-0">
    </div>
    
</template>
<script>
export default {
  
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
      const url = process.env.VUE_APP_API_CLI + '/tags'
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
<style  scoped>
body{
    background: #f2f2f2;
    font-family: 'Montserrat', sans-serif;
}
#naranja1{
    color: #FF8000;
    font-weight: 600;
    font-size: 30px;
}

.Narnjaicon{
     color: #FF8000;
     font-size: 2rem;
}
.boton-color{
    color: #FF8000;
    border:solid 2px #FF8000 ;
}
#color a{
    color:#707B7C;
}
#color a:hover{
background:#E5E7E9;
}
</style>
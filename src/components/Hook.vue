<template>
    <div id="app">
          <h1>Posts</h1>  
          <input type="text" v-model="searchTerm"> 
          <hr>
       <div v-for="post in filtersearch" :key="post.id">
           <h2>{{post.title }}</h2>
           <p>{{post.body | sniper}}</p>
         
      </div>   
    </div>
</template>


<script>
import axios from 'axios'
export default {
    name: 'Hook',
    data(){
        return {
            posts: [],
            searchTerm:''
        
        }
    },
    computed:{
        filtersearch(){
           return this.posts.filter(post=>{
                return post.body.match(this.searchTerm)
            })
        }
    },
    methods:{

 },
 created(){
     axios.get('https://jsonplaceholder.typicode.com/posts')
     .then(response => {
       // console.log(response)
       this.posts = response.data
     })
   
     .catch(error => {
         console.log(error)
     })
 }
}

</script>


<style>
   h1{
    text-align: center;
    color: red;
   }
</style>
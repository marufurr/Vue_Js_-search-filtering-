<template>
  <div id="app">
     <h2>{{ title }}</h2>
     <Navbar></Navbar>
      <Hook></Hook>
    
   </div>
</template>

<script>

import Navbar from './components/Navbar.vue'
import Hook from './components/Hook.vue'

export default {
  name: 'app',
  data(){
    return{ 
      title: 'Hurahh Vue Js',
          
    }
   
  },
  components: {
    Navbar,
    Hook

  },
  methods:{
   
    
  }
}
</script>

<style>

</style>

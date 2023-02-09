<script setup>
    import DrinkList from '../components/DrinkList.vue'
    import Header from '../components/Header.vue'
    import Footer from '../components/Footer.vue'
    import axios from 'axios'


</script>

<template>
<Header />

    <div id="drinks">
        <div class="container text-center">
            <div class="row align-items-start">
                <h1 class="title text-center">{{ message }} </h1>
            </div>
        </div>
    </div>
     
    <Footer />
    </template>
    
    <script>
    
    export default {
      
      data(){
        return {
          message: 'Welcome to my Coctail App',
        }
      }
    }
    </script>
    <style scoped>
  
    .title, h1{
      margin-bottom:5vh;
    }
   
</style>
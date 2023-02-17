<script setup>
    import DrinkList from '../components/DrinkList.vue'
    import axios from 'axios'

</script>


<template>
<div id="drinks">
        <div class="container text-center">
            <div class="row align-items-start">
                <h1 class="title text-center">{{ message }} </h1>
                <DrinkList />
            </div>
        </div>
    </div>
</template>

<script>
    
    export default {
      
      data(){
        return {
          message: 'Which is your favorite?',
          drinks: [],
        }
      },     
     methods: {
        getAllDrinks(){
          axios.get('https://thecocktaildb.com/api/json/v1/1/search.php?s=')
          .then((response) => {
            this.drinks = response.data.drinks
            const myDrink = response.data.drinks
            })
        .catch((error) =>{
          console.log(error)
        })
        
        }, 
     },
      created(){
        this.getAllDrinks()
      }
    }
    </script>
    <style scoped>
    #drinks {
        display: flex;
        justify-content: center;
        margin-top: 10vh;
        margin-bottom: 10vh;
    }
    .title, h1{
      margin-bottom:5vh;
    }
   
</style>

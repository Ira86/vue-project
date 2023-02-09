<script setup>
    import axios from 'axios'
</script>

<template>
    <!-- Bootstrap card -->
        <div v-for="drink in drinks" :key="drink.id" class="card" style="width:33%; margin-bottom:10vh;">
                <img class="card-img-top" :src="drink.strDrinkThumb" alt=""/>   
                    <div class="card-body">
                        <h5 class="card-title">{{ drink.strDrink}}</h5>
                    </div>
                      <ul class="list-group list-group-flush" style="height: 380px;">
                            <li class="list-group-item">Instructions:</li>
                            <li class="list-group-item">{{ drink.strInstructions }} </li>
                            <li class="list-group-item"> {{ drink.strIngredient1 }} </li>
                            <li class="list-group-item"> {{ drink.strIngredient2 }} </li>
                            <li class="list-group-item"> {{ drink.strIngredient3 }} </li>
                            <li class="list-group-item">{{ drink.strIngredient4 }} </li>
                            <li class="list-group-item"> {{ drink.strIngredient5 }} </li>
                    </ul>
            </div>
</template>
<script>
export default {
      
      data(){
        return {
          drinks: [],
        }
      },     
     methods: {
        getAllDrinks(){
          axios.get('https://thecocktaildb.com/api/json/v1/1/search.php?s=')
          .then((response) => {
            this.drinks = response.data.drinks
            const myDrink = response.data.drinks
            console.log(myDrink)
            })
        .catch((error) =>{
          console.log(error)
        })
        
        }, 
     },
      created(){
        this.getAllDrinks()
      },
        head(){
            return {
                
                meta: [
                    {
                        hid: 'description',
                        name: 'description',
                    }
                ]
            }
        }
    
    }
</script>
<style></style>

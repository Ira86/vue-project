<script setup>
    import DrinkList from '../components/DrinkList.vue'
    import ContactForm from '../components/ContactForm.vue'
   
    import axios from 'axios'

</script>

<template>
    <div id="drinks">
        <div class="container text-center">
            <div class="row align-items-start">
                <h1 class="title text-center">{{ message }} </h1>
                 <div class="card mb-3">
                    <img src="../assets/img/party.jpg" class="card-img-top" alt="Pool party with people">
                    <div class="card-body">
                        <h5 class="card-title">Förbereda, planera, festa!</h5>
                        <p class="card-text">Cocktailpartier är perfekta för underhållande vänner eller affärsmän, eller en kombination av de två. De är också bra för öppna hus eller mottagningar, både affärs och personligt.
                        Det genomsnittliga cocktailpartiet varar 2-3 timmar, varav gästerna snackar på en enkel spridning av mat och bjuder på bra drinkar medan de chattar med andra gäster. Det är faktiskt ganska lätt att planera och det finns så många alternativ som finns tillgängliga.</p>
                        <h5 class="card-title">Planera maten</h5>
                        <p class="card-text">En fullrätt måltid är inte nödvändig för en cocktailfest.
                        Enkel mat, såsom hors d'oeuvres och andra fingermat, gör att gästerna kan gräda under hela evenemanget, eftersom de känner behovet.
                        Några provade och sanna cocktailpartier som bruschetta och tapenade och crackers är perfekta för nästan vilken smak som helst. Även något så enkelt som en ost, kakor och skivad fruktplatta är perfekt för den avslappnade festen.
                        </p>
                        <h5 class="card-title">Planera dryck </h5>
                        <p class="card-text">Självklart är dryckerna den viktigaste delen av ett cocktailparty och det finns två alternativ.</p>
                          <ol>
                          <li>Full Bar : Om du väljer det här ger du gästerna möjlighet att välja sin favoritdryck. Det här är bra om du har en välsorterad bar eller om du är villig att köpa essentiella sprit och kan blanda upp en mängd drycker (eller ha en bra bartending guide ).</li>
                          <li><RouterLink to="/coctails">Drink Meny </RouterLink>: Det här är min favorit eftersom det uppmuntrar människor att gå ut ur sin drickrutin. Du sparar också pengar eftersom du inte behöver en fullfylld bar. Gör en lista över dryckerna (inklusive ingredienser) och sätt det på baren för att gästerna ska läsa.</li>
                          </ol>
                        <p class="card-text"><small class="text-muted">Senast uppdaterat 15 feb 2023</small></p>
                    </div>
                </div>
                  <!--- Här ska ligga formulär -->
                 <div id="contact">
                  <h1>
                     Vill du lämna feedback? Tvecka inte och kontakta oss!
                  </h1>

                    <div>
                        <ContactForm />
                    </div>
                </div>

            </div>
        </div>
    </div>
     
    </template>
    
    <script>
    
    export default {
      
      data(){
        return {
          message: 'COCKTAILPARTY',
        }
      }
    }
    </script>
    <style scoped>
  
    .title, h1{
      margin-bottom:5vh;
      margin-top:5vh;
    }
   
</style>

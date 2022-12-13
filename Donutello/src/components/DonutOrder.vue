<script setup>
import {onMounted, reactive, ref} from 'vue';

</script>

<template>
 <div class="bestellingForm">
    <h1>Bestelling formulier</h1>
    <div class="formulier">
        <h2>Contact gegevens</h2>

        <div class="infoLabel">
            <label for="name">Bedrijfsnaam</label>
            <input type="text" id="name" v-model="name">
        </div>
       
        <div class="infoLabel">
            <label for="email">Email</label>
            <input type="email" id="email" v-model="email">
        </div>
        
        <div class="infoLabel">
            <label for="phone">Telefoonnummer</label>
            <input type="tel" id="phone" v-model="phone">
        </div>
        
    </div>

    <div class="formulier">
        <h2>Donut Bestelling</h2>

        <div class="infoLabel">
            <label for="donut">Donut Naam</label>
            <input type="text" id="donut" v-model="donut">

        </div>
        
        <div class="infoLabel">
            <label for="glaze">Glazuur</label>
            <select id="glaze" v-model="donut">
                
                <option disabled value="">Kies een glazuur</option>
                <option>Chocolade</option>
                <option>Melkchocolade</option>
                <option>Witte Chocolade</option>
                <option>Aardbei</option>

            </select>
        </div>

        <div class="infoLabel">
            <label for="toppings">Topping</label>
            <select id="toppings" v-model="donut">
            
                <option disabled value="">Kies een topping</option>
                <option>Sprinkels Sweet Heaven</option>
                <option>Sprinkels Red Nose</option>
                <option>Oreo</option>
                <option>Bueno</option>

            </select> 
        </div>
      
        <div class="infoLabel">
            <label for="logo">Logo</label>
            <input type="file" id="file">
        </div>
    
        <div class="infoLabel">
            <label for="logoshape">Logo Vorm</label>
            <select id="logoshape" v-model="donut">

                <option disabled value="">Kies een vorm</option>
                <option>Rechthoek</option>
                <option>Cirkel</option>
                <option>Ovaal</option>
                <option>Driehoek</option>
                <option>Vierkant</option>

            </select>
        </div>

        <div class="infoLabel">
            <label for="amount">Aantal</label>
            <input type="text" id="donut" v-model="donut">
        </div>
        
        <div class="infoLabel">
            <label for="note">Wil je nog iet zeggen?</label>
            <textarea id="note" v-model="note"></textarea>
        </div>
        
    </div>
 </div>  
</template>

<style scoped>

.bestellingForm {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-between;
    width: 30%;
    height: 100%;
    background-color: #f5f5f5;
    padding: 2rem;
    border-radius: 1rem;
    margin: 2rem 0;
}
.formulier {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-between;
    
}
.infoLabel {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-between;
    margin: 1rem 0;
}

</style>
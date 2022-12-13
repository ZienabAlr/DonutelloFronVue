<script setup>
import {onMounted, reactive, ref} from 'vue';

const company = ref(''); 
const email = ref('');
const phone = ref('');

const donutname = ref('');
const glaze = ref('');
const toppings = ref('');
const logo = ref('');
const logoshape = ref('');
const amount = ref('');
const note = ref('');

const postOrder = ()=>{

    const data = {
        company: company.value,
        email: email.value,
        phone: phone.value,
        donutname: donutname.value,
        glaze: glaze.value,
        toppings: toppings.value,
        logo: logo.value,
        logoshape: logoshape.value,
        amount: amount.value,
        note: note.value
    }

    fetch('http://localhost:3000/api/v1/dunutello', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify(data)
    })
    .then(res => res.json())
    .then(data => console.log(data))
    .catch(err => console.log(err))
}

</script>

<template>
 <div class="bestellingForm">
    <h1>Bestelling formulier</h1>
    <div class="formulier">
        <h2>Contact gegevens</h2>

        <div class="infoLabel">
            <label for="name">Bedrijfsnaam</label>
            <input class ="inputs inputPadding" type="text" id="name" v-model="company">
        </div>
       
        <div class="infoLabel">
            <label for="email">Email</label>
            <input class ="inputs inputPadding" type="email" id="email" v-model="email">
        </div>
        
        <div class="infoLabel">
            <label for="phone">Telefoonnummer</label>
            <input class ="inputs inputPadding" type="tel" id="phone" v-model="phone">
        </div>
        
    </div>

    <div class="formulier">
        <h2>Donut Bestelling</h2>

        <div class="infoLabel">
            <label for="donut">Donut Naam</label>
            <input class ="inputs inputPadding" type="text" id="donut" v-model="donutname">

        </div>
        
        <div class="infoLabel">
            <label for="glaze">Glazuur</label>
            <select class ="inputs inputPadding" id="glaze" v-model="glaze">
                
                <option disabled value="">Kies een glazuur</option>
                <option>Chocolade</option>
                <option>Melkchocolade</option>
                <option>Witte Chocolade</option>
                <option>Aardbei</option>

            </select>
        </div>

        <div class="infoLabel">
            <label for="toppings">Topping</label>
            <select class ="inputs inputPadding" id="toppings" v-model="toppings">
            
                <option disabled value="">Kies een topping</option>
                <option>Sprinkels Sweet Heaven</option>
                <option>Sprinkels Red Nose</option>
                <option>Oreo</option>
                <option>Bueno</option>

            </select> 
        </div>
      
        <div class="infoLabel">
            <label for="logo">Logo</label>
            <input class ="inputs inputPadding" type="file" id="file">
        </div>
    
        <div class="infoLabel">
            <label for="logoshape">Logo Vorm</label>
            <select class ="inputs inputPadding" id="logoshape" v-model="logoshape">

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
            <input class ="inputs inputPadding" type="text" id="donut" v-model="amount">
        </div>
        
        <div class="infoLabel">
            <label for="note">Wil je nog iet zeggen?</label>
            <textarea class ="inputs textereaPadding" id="note" v-model="note"></textarea>
        </div>
        
    </div>

    
    <button class ="btn" @click.prevent="postOrder">Bestelling sturen</button>
    
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
    margin: 2rem 0 0 0;
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

.inputs {
    padding: 0.5rem;
    border-radius: 0.3rem;
    border: 1px solid #ccc;
    outline: none;
}

.inputPadding {
    padding: 0.5rem;
}

.textereaPadding {
    padding: 4rem 0.5rem;
    
}


.btn {
    color: rgb(247,226,0);
    font-weight: 600;
    font-family:  'Nunito', sans-serif;
    font-size: large;
    background-color: #E72770;
    border: 0;
    border-radius: 2rem;
    padding: 1rem 0;
    margin: 1rem 0;
    cursor: pointer;
}

</style>
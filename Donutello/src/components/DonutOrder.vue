<script setup>
import {onMounted, reactive, ref} from 'vue';

</script>

<template>
 <div>
    <h1>Bestelling formulier</h1>
    <div>
        <label for="name">Bedrijfsnaam</label>
        <input type="text" id="name" v-model="name">

        <label for="email">Email</label>
        <input type="email" id="email" v-model="email">

        <label for="phone">Telefoonnummer</label>
        <input type="tel" id="phone" v-model="phone">
    </div>
 </div>  
</template>

<style scoped>

</style>
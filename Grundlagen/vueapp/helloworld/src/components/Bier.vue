<template>
<div class="bier">
    <h1>{{bierText}}</h1>
    <input v-model="sorte" placeholder="Was darfst sein?">
    <h2>{{sorte}}</h2>
        <div v-for=" item in items" v-bind:key="item.id">
            {{item.marke}} - {{item.preis}}
        </div>
       
    <img :src="img.imgBier" alt="Bier" class="product" v-if="count< 7">
    <img :src="img.imgKO" alt="KO" id="ko" v-else>
    <p id="warning" v-if="count >= 7">Feierabend für Heute, Kollege! Ich ruf' dir ein Taxi!</p>
    <p v-else>{{count}}</p>
    <button v-on:click="hochDenKolben()">Rein den Zinken!</button>
</div>
    
</template>


<script>
const imgBier = require("../assets/bier.jpg")
const imgKO = require("../assets/ko.jpg")

export default {
    name: 'Bier',
    props: {
        bierText: String,
    },
    data(){
        return{
        sorte: "Helles",
        count: 0,
        img: {
            imgBier,
            imgKO,
        }
            ,
        items:[
            {marke:"Bitburger", preis:"2.2"},
            {marke:"Warsteiner", preis:"22.99"},
            {marke:"Licher", preis:"18.1"}, 
            ]
        }
    },
    methods: {
        hochDenKolben(){
            this.count++
        }
    }
}
</script>

<style scoped>
#warning{
    color:red;
    font-size: 3em;
    font-style: bold;
}
#ko{
    width: 600px;
    height: 400px;
}
</style>
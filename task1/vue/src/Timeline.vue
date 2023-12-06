<template>
    <div class="app">
        <div class="content" :class="message">        
            <div class="app__date" v-if="show_1" >
                {{ date_1 }}
            </div>
            <input class="input__date" v-else v-model="date_1">
            <img  class="app__delete" v-if="show_1" src="./assets/cross.svg" v-on:click="deleteItem">
            <img src="./assets/check.svg" class="app__delete" v-else v-on:click="addItem">
            <div class="app__title" v-if="show_1">
                {{ title_1 }}
            </div>
            <input class="input__title" v-else v-model="title_1">

            <div class="app__description" v-if="show_1">
                {{ description_1 }}
            </div>
            <input class="input__description" v-else v-model="description_1">


        </div>

    </div>
</template>

<script>
    export default {
        data () {
            return {
                title_1: this.title , 
                date_1: this.date , 
                description_1: this.description , 
                show_1: this.show , 
                message: 'notClear'
            }
        } , 
        props: ['title' , 'date' , 'description' , 'show'] ,
        methods: {
            deleteItem() {
                this.message = 'clear'
            } , 
            addItem() {
                this.show_1 = true 
            }
        } 
    } 
</script>

<style>
    .content{
        border: 2px solid black ;
        width: 300px ;  
    }

    .clear{
        display: none ; 
    }

    .app__date{
        float: right ; 
        margin: 1vh ;  
    }

    .app__delete{
        width: 20px ; 
        padding: 1vh 1.5vh; 
    }

    .app__title{
        text-align: center ; 
        font-size: 26px ; 
        padding: 6vh 0 9vh ; 
        border-bottom: 2px solid black ; 
    }

    .app__description{
        width: 90% ; 
        margin: 0 auto ;
        padding: 2vh 0 ;
        font-size: 18px ; 
    }

    .input__date{
        display: block ;
        float: right ; 
        width: 24% ;
        margin: 1vh ;
        border: none;
        outline: none;
        border-bottom: 1px solid #ccc; 
        background: #454541 ;
    }

    .input__title{
        display: block ;
        width: 40% ;
        font-size: 26px ; 
        margin: 6vh auto 9vh ; 
        border: none;
        outline: none;
        border-bottom: 1px solid #ccc; 
        background: #454541 ;
    }

    
    .input__description{
        display: block ;
        width: 90% ; 
        margin: 2vh auto 6vh ;
        font-size: 18px ; 
        border: none;
        outline: none;
        border-bottom: 1px solid #ccc; 
        border-top: 2px solid black ; 
        background: #454541 ;
    }

</style>
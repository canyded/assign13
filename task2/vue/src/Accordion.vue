<template>
    <div class="app">
        <div class="wrapper">
            <div :class="top_class">
                <div class="app__name">
                    {{ name }}
                </div>
                <img src="./assets/angle-small-up.svg" v-if="show" alt="" class="app__icon" v-on:click="close">
                <img src="./assets/angle-small-down.svg" v-else alt="" v-on:click="open">
            </div>

            <div v-if="show" class="app__title">
                {{ title }}
            </div>
        </div>
    </div>
</template> 

<script>
    export default {
        data () {
            return {
                show : false  , 
                top_class: 'app__top'
            }
        } , 
        props: ['name' , 'title'] , 
        methods: {
            open() {
                this.show = !this.show 
                this.top_class = 'app__top-s'
            } , 
            close() {
                this.show = !this.show 
                this.top_class = 'app__top'
            }
        }
    } 
</script>

<style>

    .wrapper{
        width: 94% ; 
        margin: 0 auto ; 
        padding: 0.4vh 1% ; 
        border: 1px solid black ; 
        margin-bottom: 2vh ;
    }

    .app__top{
        display: flex ; 
        justify-content: space-between ; 
    }

    .app__top-s{
        display: flex ; 
        justify-content: space-between ; 
        border-bottom: 1px solid black ; 
        margin-bottom: 1vh ; 
    }


</style>
<template> 
    <div class="app">
        <div class="app__name">
                {{ name }}
        </div>
        <div class="wrapper">
            <img src="./assets/angle-left (1).svg" alt="" class="previous" v-on:click="showPrevious">
            <div class="box" v-for="item in items">
                <img :src="require(`${item.data}`)"  class="app__icon" v-on:click="test(item.data)">
                <div class="app__title">
                    {{ item.title }}
                </div>
                <div class="app__price">
                    {{ item.price }}
                </div>
            </div>
            <img src="./assets/angle-right (1).svg" alt="" class="next" v-on:click="showNext">

        </div>
        <div class="dots">
            <div :class="dot_1"></div>
            <div :class="dot_2"></div>
            <div :class="dot_3"></div>
        </div>
    </div>
</template>

<script>
    export default {
        data () {
            return { 
                items: this.items__all.slice(0,3) , 
                dot_1: 'black_dot' , 
                dot_2: 'white_dot' ,
                dot_3: 'white_dot' ,
                first: true  ,
                last: false , 
                index: 0 
            }
        } , 
        props: ['name' , 'items__all'] , 
        methods: {
            test(text) {
                console.log(text) 
            } , 
            showNext() {
                
                this.index += 3 
                if (this.index == 6)
                    this.last = true  
                if (this.index == 9)    
                    this.index = 0 
                this.items = this.items__all.slice(this.index , this.index + 3) 
                this.first = false 
                if (this.index == 3){
                    this.dot_1 = 'white_dot' 
                    this.dot_2 = 'black_dot'
                }
                if (this.index == 6){
                    this.dot_2 = 'white_dot'
                    this.dot_3 = 'black_dot'
                }
            } , 
            showPrevious() {
                this.index -= 3 
                if (this.index == -3)
                    this.index = 6 
                this.items = this.items__all.slice(this.index , this.index + 3) 
                this.last = false 
                if (this.index == 3){
                    this.dot_3 = 'white_dot'
                    this.dot_2 = 'black_dot'
                }
                if (this.index == 0){
                    this.dot_2 = 'white_dot'
                    this.dot_1 = 'black_dot'
                }
            }
        }
    }
</script>

<style>
    
    @import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:wght@400;700&display=swap");

    *{
        margin: 0 ; 
        padding: 0 ; 
    }

    .wrapper{
        display: flex ; 
        width: 60% ; 
        margin: 0 auto ; 
        gap: 1.5% ; 
        font-family: 'Open Sans', sans-serif; 
    }

    .app__name{
        width: 50% ;    
        margin: 7vh auto 3vh; 
        text-align: center ; 
        font-size: 36px ; 
        font-family: 'Open Sans', sans-serif; 
        font-weight: 600 ; 
    }

    .box{
        background-color: #f2f2f2;
        padding: 6vh 4% 10vh ;
        text-align: center; 
        border-radius: 15px ; 
        height: 60vh ; 
    }

    .app__icon{
        width: 266px ;
        margin-bottom: 3vh ; 
    }

    .app__title{
        padding-bottom: 3vh ; 
        font-size: 14px ; 
        font-weight: 600 ; 
    }

    .app__price{
        padding-bottom: 3vh ;
        font-size: 14px ; 
    }

    .dots{
        width: 10% ;
        margin: 1vh 50%  ; 
        display: flex ;     
        gap: 6% ; 
    }

    .black_dot{
        width:fit-content; 
        height: fit-content ; 
        background: black ; 
        padding: 4px ; 
        border-radius: 50% ; 
    }

    .white_dot{
        width:fit-content; 
        height: fit-content ; 
        background: gray ; 
        padding: 4px ; 
        border-radius: 50% ; 
    }

    .previous{
        width: fit-content ; 
        position: relative ; 
        left: 7% ; 
        padding: 10px ;
        border-radius: 50% ; 
        top: 30vh ; 
        background-color: rgba(210,210,215,.64);
        height: fit-content ; 
    }

    .next{
        width: fit-content ;   
        position: relative ; 
        right: 7% ; 
        padding: 10px ; 
        border-radius: 50% ; 
        top: 30vh ; 
        background-color: rgba(210,210,215,.64);
        height: fit-content ; 
    }

</style>
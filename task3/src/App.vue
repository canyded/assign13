<template>
  <div class="appl">
    <div class="header">
      <div class="header__title">
        iPhone Accessories
      </div>
    </div>

    <app-carousel name="Power & Cables" :items__all="arr_1"></app-carousel>
  </div>  
</template>

<script>

import Carousel from './Carousel.vue'

export default {
  data() {
    return {
      arr_1: [
        {data: './assets/1/1.png' , title: '20W USB-C Power Adapter' , price: '$19.00'} , 
        {data: './assets/1/2.png' , title: 'MagSafe Charger' , price: '$39.00'} , 
        {data: './assets/1/3.png' , title: '240W USB-C Charge Cable (2 m)' , price: '$29.00'} , 
        {data: './assets/1/4.png' , title: '35W Dual USB-C Port Power Adapter' , price: '$59.00'} , 
        {data: './assets/1/5.png' , title: 'MagSafe Charger' , price: '$39.00'} , 
        {data: './assets/1/6.png' , title: '240W USB-C Charge Cable (1 m)' , price: '$19.00'} , 
        {data: './assets/1/7.png' , title: 'Thunderbolt 4 (USB‑C) Pro Cable (1 m)' , price: '$69.00'} , 
        {data: './assets/1/8.png' , title: 'Belkin BOOST↑CHARGE™ PRO 2-in-1 Wireless Charging Dock with MagSafe' , price: '$129.95'} , 
        {data: './assets/1/9.png' , title: 'Belkin BOOST↑CHARGE™ PRO 3-in-1 Wireless Charging Pad with MagSafe' , price: '$149.95'} , 
      ] , 
      arr_2: [
        {data: './assets/2/1.png' , title: 'AirTag' , price: '$29.00'} , 
        {data: './assets/2/2.png' , title: 'AirTag FineWoven Key Ring - Black' , price: '$35.00'} , 
        {data: './assets/2/3.jpeg' , title: 'AirTag Loop - White' , price: '$29.00'} , 
        {data: './assets/2/4.jpeg' , title: 'AirTag 4 pack' , price: '$99.00'} , 
        {data: './assets/2/5.png' , title: 'OtterBox Lumen Series Case for AirTag (4 pack)' , price: '$39.95'} , 
        {data: './assets/2/6.png' , title: 'Tech21 Evo Clear case for AirTag (Two Pack)' , price: '$29.95'} , 
        {data: './assets/2/7.png' , title: 'OtterBox Figura Series Case for AirTag' , price: '$19.95'} , 
        {data: './assets/2/8.png' , title: 'Belkin Secure Holder with Strap for AirTag – Black' , price: '$12.95'} , 
        {data: './assets/2/9.png' , title: 'OtterBox Rugged Case for AirTag' , price: '$19.95'} , 

      ]
    } 
  } , 
  components: {
    'app-carousel' : Carousel 
  }
}
</script>

<style>
  
  body{
    margin: 0 ; 
    padding: 0 ; 
  }

  *{
    box-sizing: border-box ; 
  }

  .header{
    padding: 2vh 0 ; 
    border-bottom: 1px solid gray ; 
  }

  .header__title{
    padding-left: 20% ; 
    font-size: 22px ; 
    font-weight: 600 ; 
    font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif ;
  }

  .appl{
    margin: 0 auto ; 
  }

</style>

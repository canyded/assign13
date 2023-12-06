<template>
  <div class="app">
    <div class="wrapper">
      <app-timeline v-for="item in timelines" :title="item.title" :show="item.show" :date="item.date" :description="item.description"></app-timeline>
      <div class="input" v-on:click="addCard">{{ button_title }}</div>
    </div>
  </div>
</template>

<script>

import Timeline from './Timeline.vue'

export default {
  data () {
    return {
      timelines: [
        {title:'New Year'  ,show:true , description: 'New Year is the time or day at which a new calendar year begins and the calendars year count increments by one.' , date:'01.01.2024'} , 
        {title:'Nauryz' ,show:true , description: 'Nauryz is a very important holiday for Kazakhs, which marks the beginning of a new year.Nauryz means ‘new day’' , date:'22.03.2024'} , 
        {title:'Kurban Ait' ,show:true , description: 'Kurban Ait, also known as Eid al-Adha or the Feast of the Sacrifice, is the holiest feast in the Islamic calendar ' , date:'16.01.2024'} ,  
      ] , 
      button_title: 'addCard' , 
      button_status: true 
    }
  } , 
  components:{
    'app-timeline': Timeline 
  } , 
  methods: {
    addCard() {
      const timeline = {
        title: '' , description:'' , show: false , date:'' 
      }
      this.timelines.push(timeline) ;
    }
  }
}
</script>

<style>

  body{
    background: #454541 ;
  }

  .wrapper{
    display: flex ; 
    flex-wrap: wrap ; 
    width: 70% ; 
    margin: 6vh auto  ;
    gap: 6vh 200px  ; 
  }

  .input{
    text-align: center ; 
    position :absolute ; 
    width: 5% ; 
    padding: 1vh 0 ;
    margin: 0 30% ; 
    bottom: 6vh ; 
    border: 2px solid ; 
  }

</style>

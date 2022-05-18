<template>
<main>
   <div class="container p-5">
    <div class="row row-cols-5">
      <CardComponent v-for="(card, index) in musicCards.response" :key="index" :card='card'/>
    </div>

  </div>

</main>
 
</template>

<script>


import axios from 'axios';
import CardComponent from './CardComponent.vue';
export default {
    name: "MainComponent",
    components: { CardComponent },
    data(){
      return{
        apiUrl:'https://flynn.boolean.careers/exercises/api/array/music',
        musicCards:[]
      }
    },
    mounted() {
      this.getApi();
    },
    methods: {
      getApi(){
        axios.get(this.apiUrl)
        .then(response => {
          console.log(response.data);
          this.musicCards = response.data;
          console.log(this.musicCards);
        })
      }
    },
}
</script>

<style lang="scss" scoped>
main{
  background-color: rgb(30, 45, 59);
  min-height: calc(100vh - 50px);
}
</style>
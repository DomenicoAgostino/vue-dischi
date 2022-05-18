<template>
<main>
   <div class="container p-5">
    <div class="row row-cols-5">
      <CardComponent />
    </div>

  </div>
</main>
 
</template>

<script>


import axios from 'axios';
import CardComponent from './CardComponent.vue';
export default {
    name: "MainComponent",
    data() {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            musiCards: [],
        };
    },
    mounted() {
        this.getApi();
    },
    methods: {
        getApi() {
            axios.get(this.apiUrl)
                .then(response => {
                this.musicCards = response.data;
            });
        }
    },
    components: { CardComponent }
}
</script>

<style lang="scss" scoped>
main{
  background-color: rgb(30, 45, 59);
  height: calc(100vh - 50px);
}
</style>
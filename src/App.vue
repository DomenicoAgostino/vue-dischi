<template>
  <div>
    <div class="container">ciao</div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'App',
  data() {
      return {
        baseURL: 'https://flynn.boolean.careers/exercises/api/array/music',
      }
  },

  component: {

  },

  mounted() {
    this.getAPI()
  },
  methods:{
    getAPI(){
      axios.get(this.baseURL)
      .then(r => {
        console.log(r.data);
      })
    }
      }
  }

</script>

<style lang="scss">
@import './assets/style/general'
</style>

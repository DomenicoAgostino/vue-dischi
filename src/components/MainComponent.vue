<template>
  <main>
    <div class="container">
      <CardComponent/>
    </div>
  </main>
</template>

<script>
import CardComponent from './CardComponent.vue';
export default {
  name: 'MainComponent',
  components: { CardComponent }
}
</script>

<style lang="scss" scoped>
main{
  background-color: rgb(30, 45, 59);
  height: calc(100vh - 50px);
}
</style>
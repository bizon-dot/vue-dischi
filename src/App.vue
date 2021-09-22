<template>
  <div id="app">
    
    <Header />
    <ContainerProducts />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import ContainerProducts from './components/ContainerProducts.vue'


export default {
  name: 'App',
  components: {
    Header,
    ContainerProducts
  }
}
</script>

<style lang="scss">
#app {

}
</style>

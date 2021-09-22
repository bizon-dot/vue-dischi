<template>
  <div class="card">
    <div class="img-album">
        <img :src="dataSong.poster">
       
    </div>

  </div>
  
</template>

<script>
export default {
  name: 'Card',
  props: ['dataSong']
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import './style/general';

     .card{
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 1em;

    }





</style>

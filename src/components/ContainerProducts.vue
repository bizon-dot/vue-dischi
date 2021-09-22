<template>
  <div class="container-album">
    <div v-for="(dataSong, index) in dataAlbum" :key="index">
      <Card :dataSong='dataSong' />
    </div>


  </div>

</template>

<script>
  import axios from 'axios';
  import Card from './Card.vue';

  export default {
    name: 'ContainerProducts',
    components: {
      Card,
    },


    data() {
      return {
        endPoint: 'https://flynn.boolean.careers/exercises/api/array/music',
        dataAlbum: [],
        loading: true
      }

    },
    created() {
      this.getData();
    },
    methods: {
      getData() {
        axios.get(this.endPoint).then(res => {
          console.log(res.data.response);
          this.dataAlbum = res.data.response;
        }).catch(err => {
          console.log("Error ", err);
        })
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import './style/general';

  .container-album {
    background-color: $bg-main;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    gap: 20px 20px;

  }
</style>
<template>
  <div v-if="!loading" class="container-album">
    <div v-for="(dataSong, index) in dataAlbum" :key="index">
      <Card :dataSong='dataSong' />
    </div>


  </div>
    <Loader v-else />
</template>

<script>
  import axios from 'axios';
  import Card from './Card.vue';
  import Loader from './Loader.vue';

  export default {
    name: 'ContainerProducts',
    components: {
      Card,
      Loader
    },


    data() {
      return {
        endPoint: 'https://flynn.boolean.careers/exercises/api/array/music',
        dataAlbum: [],
        genre: [],
        loading: true
      }

    },
    created() {
      this.getData();
    },
    methods: {
      getData() {
        axios.get(this.endPoint).then(res => {
          this.dataAlbum = res.data.response;
          this.loading = false;
          //Creo array con generi
          
           this.dataAlbum.forEach(element => {
             if (!this.genre.includes(element.genre)) {
               this.genre.push(element.genre)
             }
          });
        }).catch(err => {
          console.log("Error ", err);
        })
              console.log(this.genre);

      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import './style/general';

  .container-album {
    height: calc(100vh - 6.25em);
    width: 80%;
    margin: em(5) auto;
    background-color: $bg-black-light;
    display: grid;
    align-items: center;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    gap: em(20) em(20);

  }
</style>
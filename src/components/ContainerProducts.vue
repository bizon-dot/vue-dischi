<template>
<div>
  
</div>

</template>

<script>
import axios from 'axios';

  export default {
    name: 'ContainerProducts',

  
  data() {
    return {
      endPoint: 'https://flynn.boolean.careers/exercises/api/array/music',
      dataAlbum: [],
      loading: true
    }

  },
  created(){
      this.getData();
  },
  methods: {
    getData() {
      axios.get(this.endPoint).then ( res => {
        console.log(res.data)
      })
    }
  }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import './style/general';
</style>
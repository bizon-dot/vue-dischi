<template>
  <div class="card">
    <div class="img-album">
        <img :src="dataSong.poster">
    </div>
    <div class="title">
      <h4>{{dataSong.title.toUpperCase()}}</h4>
    </div>
    <div class="info">
      <p class="author">
        {{dataSong.author}}
      </p>
      <p class="year">
        {{dataSong.year}}
      </p>
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
      max-height: em(350);
      flex-direction: column;
      align-items: center;
      text-align: center;
      background-color: $bg-black-noir;
      padding: 0.5em;

      .img-album{
        width: em(200);
        height: em(200);
        img {
          width:80%;
        }
      }

      .title{
        h4{
          color:white;
          font-weight: 600;
        }
      
    }

      .info{
          p.author,
          p.year{
            color:#6F7C7E
          }
      
      }

     }



</style>

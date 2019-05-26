<template>
  <div id="head">
    <v-container fluid pa-0>
      <div class="yellow lighten-4 bgimg">
        <h1 class="text-xs-center pt-4 pb-2 white--text bgtext">
          <VScrollin :speed="40" :misses="2" :characters='test' >
              エンジニア向け質問サイト
          </VScrollin>
        </h1>
        <div class="text-xs-center pb-5">
          <Description />
        </div>
      </div>
    </v-container>

  </div>
</template>
<script>
  import VScrollin from 'vue-scrollin'
  import Description from './description'
  export default {
    components: { Description, VScrollin },
    data: () => ({
          test: ["エ","ン","ジ","ニ","ア","向","け","質","問","サ","イ","ト"]
    })
  }
</script>

<style>
  .bgimg {
    background-image: url('~static/qa_1.jpg');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    position: relative;
  }
  .bgimg::before {
    background-color: rgba(0,0,0,0.5);
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    content: '';
  }
  .bgtext {
    position: relative;
    width: 100%;
  }
</style>

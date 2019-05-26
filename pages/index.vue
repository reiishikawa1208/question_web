<template>
  <div class="home">
    <Head />

    <v-container>
      <Operate :page="page" v-on:get_questions="get_questions" />
      <Content :questions="questions" />
    </v-container>
  </div>
</template>

<script>
  import Head from './component/head.vue'
  import Operate from './component/operate.vue'
  import Content from './component/content.vue'
  import axios from 'axios'

  export default {
    components: { Head, Operate, Content },
    data() {
      return {
          questions: null,
          page: 1
      }
    },
    methods: {
      get_questions: function(page) {
        axios
          .get("http://192.168.8.102:3001/questions", {params: {'page': page}})
          .then(response => {
            this.questions = response.data.result;
            this.page = response.data.pages;
          })
      }
    },
    mounted() {
      this.get_questions('1')
    }
}
</script>

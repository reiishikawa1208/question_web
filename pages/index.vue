<template>
  <div class="home">
    <Head />

    <v-container>
      <Operate :page="page" v-on:get_questions="get_questions"/>
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
          page: 1,
          words: ''
      }
    },
    methods: {
      get_questions: function(page, words) {
        axios
          .get("http://140.227.202.89:3001/questions", {params: {'page': page, 'words': words}})
          .then(response => {
            this.questions = response.data.result;
            this.page = response.data.pages;
          })
      }
    },
    mounted() {
      this.get_questions(this.page,this.words)
    }
}
</script>

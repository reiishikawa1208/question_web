<template>
  <div class="home">
    <Head />

    <v-container>
      <v-flex>
        <div class="text-xs-center pb-2">
          <v-btn round color="blue-grey lighten-4" v-on:click="copy_clipboard()">
            この質問のURLをコピー
            <v-icon right>file_copy</v-icon>
          </v-btn>
        </div>
      </v-flex>
      <Content :questions="questions" />
    </v-container>
  </div>
</template>

<script>
  import Head from '../component/head.vue'
  import Content from '../component/content.vue'
  import axios from 'axios'


  export default {
    components: { Head, Content },
    data() {
      return {
          questions: null,
          test: null
      }
    },
    methods: {
      get_questions: function(id) {
        axios
          .get("http://192.168.8.102:3001/questions/" + id)
          .then(response => {
            this.questions = response.data;
          })
      },
      async copy_clipboard() {
        var url = window.location.href;
        try {
          await this.$copyText(url);
        } catch(e) {
          console.error(e);
        }
      }
    },
    mounted() {
      this.get_questions(this.$route.params.id);
    }
}
</script>

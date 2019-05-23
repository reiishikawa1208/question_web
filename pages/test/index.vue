<template>
  <div class="home">
    <v-container fluid pa-0>
      <div class="yellow lighten-4 bgimg">
        <h1 class="text-xs-center pt-4 pb-2 white--text bgtext">
          <VScrollin :speed="40" :misses="2" :characters='test' >
              初心者エンジニア向け質問サイト
          </VScrollin>
        </h1>
        <div class="text-xs-center pb-5">
          <Description />
        </div>
      </div>
    </v-container>

    <v-container>
      <v-layout row wrap align-center>
        <v-flex md2>
          <v-text-field name="search" label="search" append-icon="search"></v-text-field>
        </v-flex>
        <v-spacer></v-spacer>
        <v-flex md2>
          <v-layout row wrap>
            <v-spacer></v-spacer>
            <Qform />
          </v-layout>
        </v-flex>
      </v-layout>
      <v-expansion-panel popout light>
        <v-expansion-panel-content v-for="question in questions">
          <div slot="actions" v-if="question.icon === 'done'">
            <v-icon color="teal">done</v-icon>
          </div>
          <div slot="actions" v-else-if="question.icon === 'reject'">
            <v-icon color="error">error</v-icon>
          </div>
          <div slot="actions" v-else>
            <v-icon color="primary">$vuetify.icons.expand</v-icon>
          </div>
          <div slot="header">{{ question.title }}</div>
          <v-card>
            <v-card-text class="blue lighten-5">
              {{ question.content }}
            </v-card-text>
            <v-divider></v-divider>
            <v-card-text class="blue lighten-5">
              <v-icon>question_answer</v-icon>
              {{ question.answer }}
            </v-card-text>
          </v-card>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-container>
  </div>
</template>

<script>
  import Qform from './qform'
  import Description from './description'
  import VScrollin from 'vue-scrollin'

  export default {
    components: { Qform, Description, VScrollin },
    data() {
      return {
          test: ["初","心","者","エ","ン","ジ","ニ","ア","向","け","質","問","サ","イ","ト"],
          questions: [
            { title: "title1", content: "content", icon: "no" },
            { title: "title2", content: "content", icon: "done", answer: "answer1" },
            { title: "title3", content: "content", icon: "done", answer: "answer1" },
            { title: "title4", content: "content", icon: "reject" }
          ]
      }
    }
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

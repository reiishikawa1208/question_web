<template>
  <div id="content">
      <v-expansion-panel popout light>
        <v-expansion-panel-content v-for="question in questions" v-bind:key="question.id">
          <div slot="actions" v-if="question.comments.length > 0">
            <v-icon color="teal">done_outline</v-icon>
          </div>
          <div slot="actions" v-else-if="question.status === 'reject'">
            <v-icon color="error">error</v-icon>
          </div>
          <div slot="actions" v-else>
            <v-icon color="lime">$vuetify.icons.expand</v-icon>
          </div>
          <div slot="header">{{ question.title }}</div>
          <v-card>
            <v-card-text class="blue lighten-5">
              <p class="question_content">{{ question.content }}</p>
            </v-card-text>
            <v-divider></v-divider>
            <v-card-text class="blue lighten-5" v-for="comment in question.comments" v-bind:key="comment.content">
              <v-icon>question_answer</v-icon>
              <p class="question_comment">{{ comment.content }}</p>
            </v-card-text>
          </v-card>
        </v-expansion-panel-content>
      </v-expansion-panel>

  </div>
</template>
<script>
  export default {
    props: ['questions'],
    data: () => ({

    })
  }
</script>

<style>
  .question_content {
    white-space:pre-wrap;
  }
  .question_comment {
    white-space:pre-wrap;
  }

</style>

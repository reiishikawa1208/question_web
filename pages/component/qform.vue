<template>

<v-dialog max-width="600px" v-model="dialog">
    <v-btn color="primary" fab small slot="activator" class="ma-0">
      <v-icon>edit</v-icon>
    </v-btn>
    <v-card>
        <v-card-text>
            <v-form>
                <v-text-field name="title" label="title" v-model="title" prepend-icon="title"></v-text-field>
                <v-textarea name="content" label="content" v-model="content" prepend-icon="text_fields">
                </v-textarea>
            </v-form>
            <v-btn color="success" v-on:click="submit" :loading="loading">submit</v-btn>
        </v-card-text>
    </v-card>
</v-dialog>

</template>

<script>
import axios from 'axios'

export default {
    data() {
        return {
            title: '',
            content: '',
            loading: false,
            dialog: false
        }
    },
    methods: {
      submit: function() {
        this.loading = true;
        axios.post('http://192.168.8.102:3001/questions', {title: this.title, content: this.content})
        .then((res) => {
          this.loading = false;
          this.title   = '';
          this.content= '';
          this.dialog = false;
          this.$router.push('/questions/' + res.data.id)
        })
      }
    }
}

</script>

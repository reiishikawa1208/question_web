<template>

<v-dialog max-width="600px">
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
            <v-btn color="success">submit</v-btn>
        </v-card-text>
    </v-card>
</v-dialog>

</template>

<script>

export default {
    data() {
        return {
            title: '',
            content: ''
        }
    }
}

</script>

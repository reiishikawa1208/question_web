<template>
  <div id="operate">
      <v-layout row wrap align-center>
        <v-flex md2>
          <v-text-field name="search" label="search" append-icon="search"></v-text-field>
        </v-flex>
        <v-spacer></v-spacer>
        <v-flex md2 order-xs2 order-md3>
          <v-layout row wrap>
            <v-spacer></v-spacer>
            <Qform />
          </v-layout>
        </v-flex>
      </v-layout>
      <v-layout row wrap justify-center>
        <v-flex xs10 sm10 md5 class="text-xs-center">
          <v-pagination :length="page" v-model="current_page" class="mb-2" @input="$emit('get_questions', current_page)"></v-pagination>
        </v-flex>
      </v-layout>
  </div>
</template>

<script>
  import Qform from './qform'
  export default {
    components: { Qform },
    props: ['page'],
    data() {
      return {
        current_page: 1
      }
    }
  }
</script>

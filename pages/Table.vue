<template>
  <div>
    <v-card>
      <v-card-title>
        <v-spacer></v-spacer>
      </v-card-title>
      <v-data-table
        :headers="headers"
        :items="listdata"
        :items-per-page="5"
        :search="search"
        class="elevation-1"
      ></v-data-table>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      search: '',
      headers: [
        {
          text: 'username',
          align: 'start',
          sortable: false,
          value: 'username',
        },
        {
          text: 'tagname',
          value: 'tagname',
        },
        {
          text: 'email',
          value: 'email',
        },
        {
          text: 'pice',
          value: 'pice',
        },
      ],
    }
  },
  computed: {
    listdata: {
      get() {
        return this.$nuxt.$store.state.list
      },
    },
  },
}
</script>

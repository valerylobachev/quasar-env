<template>
  <q-page class="row items-center justify-evenly">
    Working with API server {{ apiServer }}
  </q-page>
</template>

<script lang="ts">
import { Vue, Options } from 'vue-class-component'
import { API_SERVER } from './api.service'

@Options({
  components: {  }
})
export default class PageIndex extends Vue {
  apiServer = API_SERVER
};
</script>

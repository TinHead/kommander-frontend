<template>
  <v-app dark>
    <v-content>
      <Header />
      <Main />
    </v-content>
  </v-app>
</template>

<script>
import Header from './components/Header'
import Main from './components/Main'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data () {
    return {
      //
    }
  }
}
</script>

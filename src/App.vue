<template>
  <div id="container">
    <div class="col-dev">
      <img src="./assets/images/condor.png" class="logo"/>
    </div>
    <div id="app">
      <h1>¿Cómo han impactado tu vida las comunidades tecnológicas Colombianas?</h1>
      <Quote :quote="selected.quote" :name="selected.name" :avatar="selected.avatar" v-if="selected" />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Quote from './components/Quote.vue'

export default {
  name: 'app',
  data () {
    return {
      quotes: [],
      selected: null
    }
  },
  async mounted () {
    const response = await axios('/quotes.json')
    this.quotes = response.data
    setInterval(this.selectQuote, 20000)
    this.selectQuote()
  },
  methods: {
    selectQuote () {
      const max = this.quotes.length
      const rnd = Math.floor(Math.random() * max)
      this.selected = this.quotes[rnd]
    }
  },
  components: {
    Quote
  }
}
</script>

<style lang="scss">
#app {
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 62%;
  font-size: 22px;
  margin: 0 20%;
  color: #824A21;
}
.logo {
  width: 42%;
  margin-top: 17%;
}
.col-dev {
  margin: 0%;
  position: absolute;
}
</style>

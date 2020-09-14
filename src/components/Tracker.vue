<template>
  <div id="tracker">
    <h1>Welcome to the Tracker App</h1>
    <button v-on:click="get_latest">Get Latest</button>
    <div id="data" class="hidden">
      <p>The latest count is {{this.count}}</p>
      <h4>Did you know?</h4>
      <p>{{this.fact}}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

const sleep = (millis) => new Promise(resolve => setTimeout(resolve, millis));

export default {
  name: 'Tracker',
  data: function() {
    return {
      count: 0,
      fact: ''
    }
  },
  methods: {
    get_fact: function () {
      axios.get('http://numbersapi.com/' + this.count + '/?json&notfound=floor')
          .then(response => (this.fact = response.data.text))
    },
    get_latest: function () {
      axios.get('https://api.countapi.xyz/hit/default/1ccb732e-b55a-4404-ad3f-0f99c02fe44e')
          .then(response => (this.count = response.data.value))
      document.getElementById("data").style.display = "block"
      sleep(1000).then(() => {
        this.get_fact()
      })
    }
  }
}
</script>

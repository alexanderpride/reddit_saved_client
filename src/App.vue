<template>
  <div v-if="isLoggedIn">
    <Dashboard></Dashboard>
  </div>

  <div v-else>
    <Homepage></Homepage>
  </div>
</template>

<script>

import Dashboard from "./components/Dashboard";
import Homepage from './components/Homepage.vue'

export default {
  name: 'App',
  components: {
    Homepage,
    Dashboard
  },
  data: function(){
    return {

    }
  },
  computed: {
    isLoggedIn: function () {

      // Checks that there is a cookie that is the SessionID and that it is somewhere in the cookie string
      let re = /(.*)(connect.sid=)(.*;?)/;
      return re.test(document.cookie)

    }
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Roboto+Slab&display=swap');

  #app {
    font-family: 'Roboto Slab', Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  h1{
    font-family: 'Roboto Slab', Avenir, Helvetica, Arial, sans-serif;
    font-size: 3em;
    color: #BC2C1A;
  }

  p{
    font-family: 'Roboto Slab', Avenir, Helvetica, Arial, sans-serif;
    color: #BC2C1A;
  }
</style>

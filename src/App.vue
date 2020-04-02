<template>
  <div v-if="isLinked">
    <Dashboard></Dashboard>
  </div>

  <div v-else>
    <Homepage></Homepage>
  </div>
</template>

<script>

import Dashboard from "./components/Dashboard";
import Homepage from './components/Homepage.vue';
import axios from 'axios';

export default {
    name: 'App',
    components: {
        Homepage,
        Dashboard
    },
    data: function(){
        return {
            isLinked: false
        }
    },
    methods: {

        linkToReddit: function () {
            let state = this.getUrlParameter('state');
            let code = this.getUrlParameter('code');

            if (state && code) {

                axios.request({
                  url: 'http://localhost:3000/users/link',
                  method: 'post',
                  withCredentials: true,
                  data: {
                    state: state,
                    code: code
                  }
                }).then((response) => {
                    this.isLinked = response.status === 201;
                }).catch((error) => {
                    console.log(error)
                })
            } else if (/(.*)(connect.sid=)(.*;?)/.test(document.cookie)){
              this.isLinked = true;
            }
        },
        getUrlParameter: function (name) {
            // eslint-disable-next-line no-useless-escape
            // Taken from https://davidwalsh.name/query-string-javascript
            // eslint-disable-next-line no-useless-escape
            name = name.replace(/[\[]/, '\\[').replace(/[\]]/, '\\]');
            let regex = new RegExp('[\\?&]' + name + '=([^&#]*)');
            let results = regex.exec(window.location.search);
            return results === null ? '' : decodeURIComponent(results[1].replace(/\+/g, ' '));
        }
    },
    mounted: function () {
        this.linkToReddit();
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

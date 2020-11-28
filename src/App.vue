<template>
  <div id="app" class="container">
    <Header msg="Welcome to Your Vue.js App"/>
    <Tvshows v-bind:shows = "tvshows"></Tvshows>
  </div>
</template>

<script>
import axios from 'axios'
import Header from './components/Header.vue'
import Tvshows from './components/Tvshows.vue'
import 'bootstrap';
import 'bootstrap/dist/css/bootstrap.min.css';


export default {
  name: 'App',
  components: {
    Header,
    Tvshows
    
  },
  data()
  {
    return{
      tvshows : []
    }
  },
  mounted()
  {
    axios.get(' https://api.themoviedb.org/3/tv/popular?api_key=70ef7c62eee1244489c96681175a2a0f&language=en-US&page=1')
    .then((res) => {
      this.tvshows = (res.data.results).slice(0,4)
    })
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

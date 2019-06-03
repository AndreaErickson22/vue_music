<template>
  <div class="results row d-flex justify-content-around">
    <div class="col-4 white">
    
      <h5>Search Results</h5>
      <ul>
        <li v-for="music in results" @click="setActiveMusic(music)">{{music.artistName}} :
          {{music.trackName}}</li>
      </ul>
    </div id="ActiveTunes">
    <div class="col-4">
      <details-view :music='activeMusic' v-if="activeMusic.trackName"></details-view>
    </div>
  </div>
 
</template>

<script>
  import DetailsView from '@/components/Details.vue'
  export default {
    name: '',
    data() {
      return {
        activeMusic: {}

      }
    },
    computed: {
      results() {
        return this.$store.state.results
      }
    },
    methods: {
      setActiveMusic(music) {
        this.activeMusic = music
      }

    },
    components: {
      DetailsView
    }
  }

</script>


<style>
  li {
    text-align: left;
    font-size: 12px;
    font-weight: 500;
  }

  .yellow {
    background-color: white;
  }

  .results {
    margin-top: 100px;
    background-color:white;
    z-index: 3;
  }

  .white {
    padding-top: 20px;
    overflow: scroll;
    height: 500px;
    background-color: rgba(0, 255, 255, 0.288);
margin-bottom: 10px;
  
  }
</style>
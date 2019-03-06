<template>
  <div class="results row d-flex justify-content-around">
    <div class="col-4 white">
      <h1>Results</h1>
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
  }

  .yellow {
    background-color: white;
  }

  .results {
    margin-top: 100px;
    background-color: aqua;
    z-index: 3;
  }

  .white {
    overflow: scroll;
    height: 500px;
  }
</style>
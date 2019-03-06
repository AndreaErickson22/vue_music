<template>
  <div class="row">
    <div class="details col fluid white">
      <div class="card-stuff">
        <img class="image-stuff" :src="music.artworkUrl100.replace(/100x100/g, '1000x1000')">

        <div class="card-body">
          <h2>{{music.artistName}}</h2>
          <h2>{{music.trackName}}</h2>
          <h3>${{music.collectionPrice}}</h3>

          <audio controls>
            <source :src="music.previewUrl" type="audio/mpeg">
          </audio>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Details",
    props: ["music"],

    data() {
      return {};
    },
    computed: {},
    methods: {},
    watch: {
      music: {
        handler: (val, oldVal) => {
          document.getElementsByTagName("audio")[0].load();
        }
      }
    }
  };
</script>

<style>
  h1 {
    font-size: 25px;
    color: white;
  }

  h2 {
    font-size: 15px;
    font-style: italic;
  }

  h3 {
    font-size: 12px;
    font-style: oblique;
  }

  .image-stuff {
    z-index: 12;
    max-height: 200px;
    max-width: 200px;
  }
</style>
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
audio {
  width: 100%;
}
h1 {
  font-size: 25px;
  color: white;
  font-weight: 700;
}

h2 {
  font-weight: 700;
  font-size: 15px;
  font-style: italic;
  color: white;
}

h3 {
  font-weight: 700;
  font-size: 12px;
  font-style: oblique;
  color: white;
}

.image-stuff {
  z-index: 12;
  max-height: 200px;
  max-width: 200px;
}
.card-stuff {
  padding-top: 20px;
  background-color: rgb(83, 83, 83);
}
.details {
  margin-top: 20px;
}
</style>
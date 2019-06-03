<template>
  <div class="home container-fluid">
    <div style="background-image: url(./link/to/image.png)">
      <header class="row">
        <div class="col-6">
          <h1>Find Your Favorite Music</h1>
        </div>

        <div class="col-3">
          <form @submit.prevent="search" class="form-group">
            <input type="text" placeholder="Enter an artist or song" v-model="query" required>
          </form>
          <button type="submit" class="btn btn-info">Music Search</button>
        </div>
      </header>
      <results></results>
    </div>
  </div>
</template>

<script>
import Results from "@/components/Results.vue";
export default {
  name: "home",
  data() {
    return {
      query: ""
    };
  },
  computed: {},
  methods: {
    search() {
      this.$store.dispatch("getMusicByArtist", this.query);
    }
  },
  components: {
    Results
  }
};
</script>

<style>
input {
  margin-top: 10px;
  width: 100%;
}

.home {
  background-color: rgb(122, 0, 128);
}

header {
  height: 100px;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 2;
  background-color: rgb(83, 83, 83);
}
button {
  background-color: lightgreen;
}
</style>
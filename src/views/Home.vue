<template>
  <div style="background-image: url(./link/to/image.png)" &#x3C;div class="home container-fluid">
    <header class="row">
      <div class="col-3 text-center">
        <h1>Your Favorite Music</h1>
      </div>

      <div class="col-3">
        <form @submit.prevent="search" class="form-group">
          <input type="text" placeholder="Title...." v-model="query" required>
          <button type="submit" class="btn btn-info">Search</button>
        </form>
      </div>
    </header>
    <results></results>
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
.home {
  background-color: rgb(122, 0, 128);
}

header {
  height: 100px;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 2;
  background-color: blueviolet;
}
</style>


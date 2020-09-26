<template>
   <div class="container">

    <b-container fluid class="bv-example-row mb-4" >
      <input type="text" v-model="keyword" /> 
   <div class="container-search">
      <b-button pill variant="pink" @click="searchData()" > Search music</b-button>
    </div>
      <!-- {{resultData}} -->
    </b-container>
    <b-container fluid class="bv-example-row">
      <b-row align-h="around mr-4 ml-4">
        <b-card bg-variant="light"
          v-for="data in resultData"
          :key="data.trackId"
          :title="data.trackName"
          :img-src="data.artworkUrl60"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem"
          class="mb-2"
        >
          <audio controls>
            <source :src="data.previewUrl" type="audio/mpeg" />
          </audio>
          <b-button :href="data.trackViewUrl" variant="dark"
            >Go preview</b-button >
            
        </b-card>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      resultData: null,
      keyword:''
    };
  },
 methods: {
    searchData() {
      console.log("searchData");
      axios.get("https://itunes.apple.com/search?term=" + this.keyword + "")
        .then((response) => {
          this.resultData = response.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style>
.container {
  position: relative;
  width: 100%;
  max-width: 400px;
}
 .container-search {
  position: relative;
  font-size: 40px;
}

</style>
<template>
  <div class="containr">
      <input type="text" v-model="keyword" />
    <button @click="searchData()">Search Anime</button>
    <!--{{resultData}}-->
    <div >
     <!-- id ={{data.mal_id}}
      ชื่อ ={{data.title}}
      รายละเอียด ={{data.synopsis}}
      รูป ={{data.image_url}} -->
      <b-card-group columns>
      <b-card v-for="data in resultData" :key="data.mal_id"
        :title="data.title"
        :img-src="data.image_url"
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 20rem;"
        class="mb-2"
      >
        <b-card-text>{{data.synopsis}}</b-card-text>
        <b-button href="data.url" variant="primary">Go somewhere</b-button>
      </b-card>
      </b-card-group>
    </div>
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
      axios
        .get("https://api.jikan.moe/v3/search/anime?q="+this.keyword+"&page=1")
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
</style>
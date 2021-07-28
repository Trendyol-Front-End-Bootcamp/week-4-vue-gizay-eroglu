<template>
  <div class="home">
    <Header />
    <div class="searchArea">
      <input
        type="text"
        placeholder="Search a Starship Name or Model"
        id="name"
        name="name"
        v-model="params.search"
      />
      <button @click="filterStarships" class="searchButton">Search</button>
    </div>
    <div v-if="starships.length > 0" class="gridStructure">
      <Card
        v-for="(starship, index) in starships"
        :key="index"
        :starship="starship"
      />
    </div>
    <div v-else-if="isLoading==true" class="shipsLoading">
      Ships Loading . . 
    </div>
    <div v-else>
      <NotFound />
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import NotFound from "@/components/NotFound.vue";
import Card from "@/components/Card.vue";
import axios from "axios";

const URL = "https://swapi.dev/api/starships/";

export default {
  name: "Home",

  components: {
    Header,
    Card,
    NotFound,
  },

  data() {
    return {
      isLoading:true,
      starships: [],
      params: {},
    };
  },
  methods: {
    async getAllStarships(params) {
      const response = await axios.get(`${URL}`, { params });
      
      if (response.status === 200 && response.data.results.length > 0) {
        this.isLoading=false;
        return response.data.results;
      } else {
        return [];
      }
    },
    async getStarships(params) {
      this.starships = await this.getAllStarships(params);
    },
    async filterStarships() {
      await this.getStarships(this.params);
    },
  },
  async mounted() {
    await this.getStarships({});
  },
};
</script>
<style scoped lang="scss">
@import "../style/style.scss";
</style>

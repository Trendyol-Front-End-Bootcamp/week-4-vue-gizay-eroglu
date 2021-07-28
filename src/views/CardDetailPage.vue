<template>
  <div class="cardDetailPage">
    <GoBackToHomePage />
    <CardDetail :starship="starship" />
  </div>
</template>

<script>
import GoBackToHomePage from "@/components/GoBackToHomePage.vue";
import CardDetail from "@/components/CardDetail.vue";
import axios from "axios";

const URL = "https://swapi.dev/api/starships/";

export default {
  name: "CardDetailPage",
  components: {
    GoBackToHomePage,
    CardDetail,
  },
  data() {
    return {
      starship: {},
    };
  },
  methods: {
    async getStarshipDetial() {
      const id = this.$route.params.id;
      const response = await axios.get(`${URL}${id}`);

      if (response.status === 200) {
        this.starship = response.data;
      } else {
        this.starship = {};
      }
    },
  },
  async mounted() {
    await this.getStarshipDetial();
  },
};
</script>

<style lang="scss">
@import "../style/style.scss";
</style>

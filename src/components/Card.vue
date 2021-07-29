<template>
  <div class="card">
    <router-link :to="`/cardDetailPage/${getStarshipId}`" class="router-link">
      <img src="../assets/starship.jpg" alt="Starship" />
      <p>
        <span>Name: </span>
        {{ starship.name }}
      </p>
      <p>
        <span>Model: </span>
        {{ starship.model }}
      </p>
      <p>
        <span>Hyperdrive rating: </span>
        {{ starship.hyperdrive_rating }}
      </p>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    starship: {
      type: Object,
    },
  },
  data() {
    return {};
  },
  computed: {
    getStarshipId() {
      return this.starship.url.split("/")[5];
    },
  },
};
</script>
<style scoped lang="scss">
@import "../style/pages/homePage.scss";
</style>

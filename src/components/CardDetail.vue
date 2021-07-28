<template>
  <div class="pageDiv">
    <div class="cardDetail">
      <img
        src="../assets/starship.jpg"
        alt="Starship"
        class="cardDetailPageImg"
      />
      <div class="cardText">
        <p>
          <span>Name:</span>
          {{ starship.name }}
        </p>
        <p>
          <span>Model:</span>
          {{ starship.model }}
        </p>
        <p>
          <span>Hyperdrive rating:</span>
          {{ starship.hyperdrive_rating }}
        </p>
        <p>
          <span>Passengers:</span>
          {{ starship.passengers }}
        </p>
        <p>
          <span>Max Atmosphering Speed:</span>
          {{ starship.max_atmosphering_speed }}
        </p>
        <p>
          <span>Manufacturer:</span>
          {{ starship.manufacturer }}
        </p>
        <p>
          <span>Crew:</span>
          {{ starship.crew }}
        </p>
        <p>
          <span>Cargo Capacity:</span>
          {{ starship.cargo_capacity }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "cardDetail",
  props: {
    starship: {
      type: Object,
    },
  },
};
</script>

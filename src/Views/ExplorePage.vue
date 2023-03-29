<template>
  <HeaderHero
    title="Explore The Scenic Rim"
    :backgroundImage="backgroundImage"
  />
  <section>
    <div class="container">
      <div class="row">
        <div class="col-sm-6 col-md-6 col-md-6">
          <GMapMap
            :center="center"
            :zoom="14"
            style="height: 40vh; width: 100%"
          >
            <GMapCluster>
              <GMapMarker
                :key="index"
                v-for="(m, index) in markers"
                :position="m.position"
                :clickable="true"
                :draggable="true"
                @click="center = m.position"
              />
            </GMapCluster>
            <GMapMarker :position="center" />
          </GMapMap>
        </div>
        <div class="col">
          The Scenic Rim is a picturesque region located in southeast
          Queensland, Australia. Known for its stunning landscapes, charming
          towns, and unique experiences, the Scenic Rim is a great spot to visit
          for those looking for an escape from the hustle and bustle of city
          life. Visitors can explore the region's beautiful national parks,
          indulge in delicious local produce, and take part in a range of
          outdoor activities such as hiking, camping, and horse riding. With its
          friendly locals and relaxed atmosphere, the Scenic Rim offers a truly
          authentic Australian experience that is not to be missed. Come see for
          yourself why The Scenic Rim has been ranked in the world's top 10
          regions to travel to in 2022 by Lonely Planet.
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import HeaderHero from "../components/HeaderHero.vue";
export default {
  components: { HeaderHero },
  name: "App",
  data() {
    return {
      backgroundImage: require("../assets/Boonah.jpg"),
      center: { lat: -28.170486, lng: 152.671196 },

      markers: [
        {
          position: {
            lat: -28.170486,
            lng: 152.671196,
          },
        }, // Along list of clusters
      ],
    };
  },
};
</script>
<style scoped>
section {
  margin-top: 100px;
  margin-bottom: 50px;
}
.container {
  height: auto;
  padding-bottom: 100px;
  display: flex;
}
</style>

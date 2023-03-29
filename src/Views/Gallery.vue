<template>
  <div class="gallery">
    <HeaderHero title="Gallery" :background-image="backgroundImage" />
    <div class="container">
      <div class="row">
        <div class="col-lg-12">
          <h1>The Property</h1>
          <hr />
          <div class="card-container d-flex flex-wrap">
            <div
              v-for="(item, index) in house"
              :key="index"
              class="images col-lg-4 col-md-6 col-sm-6"
            >
              <a
                href="https://therichpost.com/wp-content/uploads/2021/05/bootstrap5-carousel-slider-img2.jpg"
              >
                <img
                  :src="item.src"
                  class="d-block w-100 glightbox"
                  style="border-radius: 5px"
                />
              </a>
            </div>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-12">
          <h1>The Animals</h1>
          <hr />
          <div class="card-container d-flex flex-wrap">
            <div
              v-for="(item, index) in animals"
              :key="index"
              class="images col-lg-4 col-md-6 col-sm-6"
            >
              <a
                href="https://therichpost.com/wp-content/uploads/2021/05/bootstrap5-carousel-slider-img2.jpg"
              >
                <img
                  :src="item.src"
                  class="d-block w-100 glightbox"
                  style="border-radius: 5px"
                />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderHero from "../components/HeaderHero.vue";
import "glightbox/dist/css/glightbox.css";
import "glightbox/dist/js/glightbox.js";
import GLightbox from "glightbox";
export default {
  name: "GalleryPage",
  components: { HeaderHero },
  data() {
    return {
      backgroundImage: require("../assets/OutsideHouseView.jpg"),
      house: [
        {
          src: require("../assets/OutsideHouse.jpg"),
        },
        {
          src: require("../assets/OutsideHouse.jpg"),
        },
        {
          src: require("../assets/OutsideHouseView.jpg"),
        },
        {
          src: require("../assets/Boonah.jpg"),
        },
        {
          src: require("../assets/OutsideHouseView.jpg"),
        },
        {
          src: require("../assets/OutsideHouseView.jpg"),
        },
      ],
      animals: [
        {
          src: "https://a0.muscache.com/im/pictures/miso/Hosting-53084565/original/5ca02cc9-253c-49fb-adfc-3be74e6ef4c8.jpeg?im_w=1440",
        },
        {
          src: "https://a0.muscache.com/im/pictures/miso/Hosting-53084565/original/66740060-1123-49b7-9e05-d977195c0d32.jpeg?im_w=1440",
        },
        {
          src: "https://a0.muscache.com/im/pictures/miso/Hosting-53084565/original/6636776a-aec5-4de1-8cb9-4fe370ec7499.jpeg?im_w=1440",
        },
        {
          src: "https://a0.muscache.com/im/pictures/miso/Hosting-53084565/original/7570ed53-bb53-429d-a20a-64772b75fba0.jpeg?im_w=1440",
        },
        {
          src: "https://a0.muscache.com/im/pictures/miso/Hosting-53084565/original/6636776a-aec5-4de1-8cb9-4fe370ec7499.jpeg?im_w=1440",
        },
        {
          src: "https://a0.muscache.com/im/pictures/miso/Hosting-53084565/original/7570ed53-bb53-429d-a20a-64772b75fba0.jpeg?im_w=1440",
        },
      ],
    };
  },

  mounted() {
    //lightbox settings
    this.lightbox = GLightbox({
      selector: ".glightbox",
    });
  },
};
</script>

<style>
.images {
  padding: 10px;
  background-color: rgb(255, 250, 250);
}
h1 {
  margin-top: 50px;
}
.gallery {
  background-color: rgb(255, 248, 248);
}
</style>

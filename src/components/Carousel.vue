<template>
  <div id="carousel">
    <Slider animation="fade" v-model="sliderValue" :duration="5000" :speed="1000">
      <SliderItem v-for="(i, index) in list" :key="index" @click="changeIndex(1);" :style="i">
        <img class="c-img" :src="i.img" alt />
      </SliderItem>
    </Slider>
  </div>
</template>

<script>
import { Slider, SliderItem } from "vue-easy-slider";

export default {
  name: "Carousel",
  components: {
    Slider,
    SliderItem
  },
  data() {
    return {
      list: [],
      sliderValue: 2
    };
  },
  methods: {
    changeIndex(index) {
      this.sliderValue = index;
    }
  },
  mounted() {
    setTimeout(
      () =>
        (this.list = [
          {
            backgroundColor: "#3f51b5",
            width: "100%",
            height: "100%",
            img: require("../assets/carousel/1.jpg")
          },
         
          {
            backgroundColor: "#f44336",
            width: "100%",
            height: "100%",
            img: require("../assets/carousel/3.jpg")
          },
          {
            backgroundColor: "#eee",
            width: "100%",
            height: "100%",
            img: require("../assets/carousel/4.jpg")
          },
          {
            backgroundColor: "#eee",
            width: "100%",
            height: "100%",
            img: require("../assets/carousel/5.jpg")
          }
        ]),
      1000
    );
  }
};
</script>

<style lang="scss" scopped>
#carousel {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  position: relative;

  .slider {
    width: 100%;
    height: 80vh !important;
    border-radius: 5px;
  }

  .c-img {
    width: 100%;
    height: 100vh;
    object-fit: cover;
    object-position: bottom;
    border-radius: 5px;
  }

}

p {
  margin: 0;
}
</style>

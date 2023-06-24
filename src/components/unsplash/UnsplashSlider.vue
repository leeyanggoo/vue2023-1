<template>
  <div class="unsplash__slider">
    <swiper
      :loop="true"
      :modules="modules"
      :slides-per-view="4"
      :speed="3000"
      :space-between="10"
      :autoplay="{
        delay: 0,
        disableOnInteraction: false,
      }"
    >
      <swiper-slide v-for="(sliderImage, index) in sliderImages" :key="index">
        <a
          :href="`https://unsplash.com/photos/${sliderImage.id}`"
          target="_blank"
        >
          <img
            :src="sliderImage.urls.full"
            :alt="sliderImage.alt_description"
          />
        </a>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { Autoplay } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

export default {
  props: {
    sliderImages: {
      type: Array,
      required: true,
    },
  },

  components: {
    Swiper,
    SwiperSlide,
  },

  setup() {
    return {
      modules: [Autoplay],
    };
  },
};
</script>
<style lang="scss">
// unsplash__slider
.unsplash__slider {
  margin-bottom: 50px;
  .swiper-wrapper {
    transition-timing-function: linear;
  }
}
</style>

<template>
  <div class="youtube__slider">
    <swiper
      :loop="true"
      :modules="modules"
      :slides-per-view="4"
      :speed="3000"
      :space-between="0"
      :autoplay="{
        delay: 0,
        disableOnInteraction: false,
      }"
    >
      <swiper-slide v-for="(youtube, index) in youtubes" :key="index">
        <a
          :href="`https://www.youtube.com/watch?v=${youtube.id.videoId}`"
          target="_blank"
        >
          <img
            :src="youtube.snippet.thumbnails.high.url"
            :alt="youtube.snippet.title"
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
    youtubes: {
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
// youtube__slider
.youtube__slider {
  margin-bottom: 50px;
  .swiper-wrapper {
    transition-timing-function: linear;
  }
}
</style>

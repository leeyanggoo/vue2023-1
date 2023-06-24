<template>
  <div className="movie_slider">
    <swiper
      :loop="true"
      :modules="modules"
      :slides-per-view="3"
      :speed="1000"
      :space-between="20"
      navigation
      :pagination="{ clickable: true }"
      :autoplay="{
        delay: 2000,
        disableOnInteraction: false,
      }"
    >
      <swiper-slide v-for="(movie, index) in movies" :key="index">
        <a
          :href="`https://www.themoviedb.org/movie/${movie.id}?language=ko`"
          target="_blank"
        >
          <img
            :src="`https://image.tmdb.org/t/p/w1280/${movie.backdrop_path}`"
            :alt="movie.title"
          />
        </a>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
import { Navigation, Pagination, Autoplay } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

export default {
  props: {
    movies: {
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
      modules: [Navigation, Pagination, Autoplay],
    };
  },
};
</script>
<style lang="scss">
// movie_slider
.movie_slider {
  margin-bottom: 50px;
}
</style>

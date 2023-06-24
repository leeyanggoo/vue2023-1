<template>
  <section id="movieSection" :class="attr">
    <div class="movie__inner">
      <div class="movie__header container">
        <h3>문학 유튜브 추천</h3>
        <p>
          더 다양한 강의가 유튜브를 통해 제공되고 있습니다.
          <br />
          구독과 좋아요! 부탁드립니다.
        </p>
        <router-link to="/movie" class="button-blue"> 자세히 보기 </router-link>
      </div>
      <div class="movie__body">
        <div class="movie__item">
          <swiper
            :loop="true"
            :modules="modules"
            :slides-per-view="6"
            :speed="3000"
            :autoplay="{
              delay: 0,
              disableOnInteraction: false,
            }"
          >
            <swiper-slide v-for="(movie, index) in movies" :key="index">
              <a
                :href="`https://www.themoviedb.org/movie/${movie.id}?language=ko`"
                target="_blank"
              >
                <img
                  :src="`https://image.tmdb.org/t/p/w500/${movie.backdrop_path}`"
                  :alt="movie.title"
                />
              </a>
            </swiper-slide>
          </swiper>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import { Autoplay } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

export default {
  props: {
    attr: String,
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
      modules: [Autoplay],
    };
  },
};
</script>
<style lang="scss">
// movies__wrap
.movie__inner {
  .movie__header {
    h3 {
      font-size: 50px;
      margin-bottom: 40px;
    }
    p {
      font-size: 22px;
      font-weight: 300;
      margin-bottom: 60px;
    }
    a {
      border-radius: 50px;
      margin-bottom: 100px;
    }
  }
}
</style>

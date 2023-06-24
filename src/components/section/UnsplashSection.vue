<template>
  <section id="unsplashSection" :class="attr">
    <div class="unsplash__inner">
      <div class="unsplash__header container">
        <h3>시요일 감성</h3>
        <p>
          시인은
          <br />
          관찰하는 사람이다.
        </p>
        <router-link to="/unsplash" class="button-green">
          자세히 보기
        </router-link>
      </div>
      <div class="unsplash__body">
        <div class="unsplash__item">
          <swiper
            :loop="true"
            :modules="modules"
            :slides-per-view="9"
            :speed="3000"
            :autoplay="{
              delay: 0,
              disableOnInteraction: false,
            }"
          >
            <swiper-slide
              v-for="(verticalImage, index) in verticalImages"
              :key="index"
            >
              <a
                :href="`https://unsplash.com/photos/${verticalImage.id}`"
                target="_blank"
              >
                <img
                  :src="verticalImage.urls.thumb"
                  :alt="verticalImage.alt_description"
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
    verticalImages: {
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
// unsplash__wrap
.unsplash__inner {
  .unsplash__header {
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

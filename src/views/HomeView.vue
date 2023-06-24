<template>
  <main>
    <SliderSection attr="slider__wrap NanumM" />
    <IntroSection attr="intro__wrap section SCoreDream" />
    <PortSection attr="port__wrap section center bg-blue NanumM" />
    <YoutubeSection attr="youtube__wrap section NanumM" :youtubes="youtubes" />
    <UnsplashSection
      attr="unsplash__wrap section bg-blue NanumM"
      :verticalImages="verticalImages"
    />
    <MovieSection attr="movies__wrap section NanumM" :movies="movies" />
  </main>
</template>

<script>
import IntroSection from "@/components/section/IntroSection.vue";
import SliderSection from "@/components/section/SliderSection.vue";
import PortSection from "@/components/section/PortSection.vue";
import MovieSection from "@/components/section/MovieSection.vue";
import UnsplashSection from "@/components/section/UnsplashSection.vue";
import YoutubeSection from "@/components/section/YoutubeSection.vue";
import { ref } from "vue";

export default {
  components: {
    IntroSection,
    SliderSection,
    PortSection,
    MovieSection,
    UnsplashSection,
    YoutubeSection,
  },

  setup() {
    const verticalImages = ref([]);
    const youtubes = ref([]);
    const movies = ref([]);

    var requestOptions = {
      method: "GET",
      redirect: "follow",
    };

    // unsplash
    const VerticalImages = () => {
      fetch(
        "https://api.unsplash.com/photos?client_id=jH0imhhs5rWunB3C4xoZHkzW4cuMAi0DT3c3uBNHn54&per_page=28",
        requestOptions
      )
        .then((response) => response.json())
        .then((result) => {
          verticalImages.value = result.filter(
            (image) => image.height > image.width
          );
        })
        .catch((error) => console.log(error));
    };
    VerticalImages();

    // youtube
    const TopYoutubes = () => {
      fetch(
        "https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=%EB%AC%B8%ED%95%99&type=video&key=AIzaSyC5_JL1EdBzYtbTM03behVWBCGgNq_Y-18"
      )
        .then((response) => response.json())
        .then((result) => {
          youtubes.value = result.items;
        })
        .catch((error) => console.log(error));
    };
    TopYoutubes();

    // movie
    const TopMovies = () => {
      fetch(
        "https://api.themoviedb.org/3/movie/popular?api_key=35deb8704c2372673b61a5e807e3688e&language=ko-KR&query=SEARCH_QUERY&page=1&include_adult=false&limit=30"
      )
        .then((response) => response.json())
        .then((result) => {
          movies.value = result.results;
        })
        .catch((error) => console.log(error));
    };
    TopMovies();

    return {
      verticalImages,
      VerticalImages,
      youtubes,
      TopYoutubes,
      movies,
      TopMovies,
    };
  },
};
</script>

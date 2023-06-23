<template>
  <ContTitle title="movies" />
  <MovieSlider :movies="movies" />
  <MovieSearch @search="SearchMovie" />
  <MovieTag />
  <MovieCont :movies="movies" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import MovieSlider from "@/components/movie/MovieSlider.vue";
import MovieSearch from "@/components/movie/MovieSearch.vue";
import MovieTag from "@/components/movie/MovieTag.vue";
import MovieCont from "@/components/movie/MovieCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    MovieSlider,
    MovieSearch,
    MovieTag,
    MovieCont,
  },

  setup() {
    const movies = ref([]);

    const TopMovies = () => {
      fetch(
        "https://api.themoviedb.org/3/movie/popular?api_key=35deb8704c2372673b61a5e807e3688e&language=ko-KR&query=SEARCH_QUERY&page=1&include_adult=true&limit=30"
      )
        .then((response) => response.json())
        .then((result) => {
          movies.value = result.results;
        })
        .catch((error) => console.log(error));
    };
    TopMovies();

    const SearchMovie = async (query) => {
      await fetch(
        `https://api.themoviedb.org/3/search/movie?api_key=35deb8704c2372673b61a5e807e3688e&language=ko-KR&query=SEARCH_QUERY&page=1&include_adult=true&limit=30&query=${query}`
      )
        .then((response) => response.json())
        .then((result) => {
          movies.value = result.results;
        })
        .catch((error) => console.log(error));
    };

    return {
      movies,
      TopMovies,
      SearchMovie,
    };
  },
};
</script>

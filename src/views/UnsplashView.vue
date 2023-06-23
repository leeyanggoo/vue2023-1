<template>
  <ContTitle title="unsplash" />
  <UnsplashSlider />
  <UnsplashSearch @search="SearchImage" />
  <UnsplashTag />
  <UnsplashCont :images="images" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import UnsplashSlider from "@/components/unsplash/UnsplashSlider.vue";
import UnsplashSearch from "@/components/unsplash/UnsplashSearch.vue";
import UnsplashTag from "@/components/unsplash/UnsplashTag.vue";
import UnsplashCont from "@/components/unsplash/UnsplashCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    UnsplashSlider,
    UnsplashSearch,
    UnsplashTag,
    UnsplashCont,
  },

  setup() {
    const images = ref([]);
    var requestOptions = {
      method: "GET",
      redirect: "follow",
    };

    const TopUnsplash = () => {
      fetch(
        "https://api.unsplash.com/photos?client_id=jH0imhhs5rWunB3C4xoZHkzW4cuMAi0DT3c3uBNHn54&per_page=30",
        requestOptions
      )
        .then((response) => response.json())
        .then((result) => {
          images.value = result;
        })
        .catch((error) => console.log(error));
    };
    TopUnsplash();

    const SearchImage = async (query) => {
      await fetch(
        `https://api.unsplash.com/search/photos?client_id=jH0imhhs5rWunB3C4xoZHkzW4cuMAi0DT3c3uBNHn54&per_page=30&query=${query}`
      )
        .then((response) => response.json())
        .then((result) => {
          images.value = result.results;
        })
        .catch((error) => console.log(error));
    };

    return {
      images,
      TopUnsplash,
      SearchImage,
    };
  },
};
</script>

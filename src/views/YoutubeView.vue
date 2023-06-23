<template>
  <ContTitle title="youtube" />
  <YoutubeSlider />
  <YoutubeSearch />
  <YoutubeTag />
  <YoutubeCont :youtubes="youtubes" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSlider from "@/components/youtube/YoutubeSlider.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";
import { ref } from "vue";

export default {
  components: {
    ContTitle,
    YoutubeSlider,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },

  setup() {
    const youtubes = ref([]);

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

    return {
      youtubes,
      TopYoutubes,
    };
  },
};
</script>

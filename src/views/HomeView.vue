<template>
  <main>
    <SliderSection attr="slider__wrap NanumM" />
    <IntroSection attr="intro__wrap bg-blue section SCoreDream" />
    <MemberSection attr="member__wrap section center" />
    <PortSection attr="port__wrap section center" />
    <YoutubeSection attr="youtube__wrap section NanumM" />
    <UnsplashSection attr="unsplash__wrap section bg-blue NanumM" />
    <MovieSection attr="movies__wrap section NanumM" />
  </main>
</template>

<script>
import IntroSection from "@/components/section/IntroSection.vue";
import SliderSection from "@/components/section/SliderSection.vue";
import MemberSection from "@/components/section/MemberSection.vue";
import PortSection from "@/components/section/PortSection.vue";
import MovieSection from "@/components/section/MovieSection.vue";
import UnsplashSection from "@/components/section/UnsplashSection.vue";
import YoutubeSection from "@/components/section/YoutubeSection.vue";

export default {
  components: {
    IntroSection,
    SliderSection,
    MemberSection,
    PortSection,
    MovieSection,
    UnsplashSection,
    YoutubeSection,
  },
};
</script>

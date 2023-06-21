<template>
  <div>
    <HeaderCont />
    <router-view />
    <FooterCont />
  </div>
</template>

<script>
import HeaderCont from "@/components/layout/HeaderCont.vue";
import FooterCont from "@/components/layout/FooterCont.vue";

export default {
  components: {
    HeaderCont,
    FooterCont,
  },
};
</script>

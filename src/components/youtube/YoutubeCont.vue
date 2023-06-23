<template>
  <div class="youtube__cont container">
    <ul>
      <li v-for="(youtube, index) in youtubes" :key="index">
        <img :src="youtube.snippet.thumbnails.medium.url" alt="유튜브" />
        <span>{{ youtube.snippet.title }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    youtubes: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.youtube__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;

    li {
      width: 24%;
      margin-bottom: 4%;

      img {
        border-radius: 20px;
        width: 100%;
      }

      span {
        display: block;
        margin: 4px 0;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        -webkit-line-clamp: 1; /* 라인수 */
        -webkit-box-orient: vertical;
        word-wrap: break-word;
      }
    }
  }
}
</style>

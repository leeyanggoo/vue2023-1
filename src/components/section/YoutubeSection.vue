<template>
  <section id="youtubeSection" :class="attr">
    <div class="youtube__inner">
      <div class="youtube__header container">
        <h3>문학 유튜브 추천</h3>
        <p>
          더 다양한 강의가 유튜브를 통해 제공되고 있습니다.
          <br />
          구독과 좋아요! 부탁드립니다.
        </p>
        <a href="/" class="button-red"> 자세히 보기 </a>
      </div>
      <div class="youtube__body">
        <div class="youtube__item">
          <div>
            <img src="@/assets/images/youtube/youtube01.png" alt="유튜브" />
          </div>
          <div>
            <img src="@/assets/images/youtube/youtube02.png" alt="유튜브" />
          </div>
          <div>
            <img src="@/assets/images/youtube/youtube03.png" alt="유튜브" />
          </div>
          <div>
            <img src="@/assets/images/youtube/youtube04.png" alt="유튜브" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: {
    attr: String,
  },
};
</script>
<style lang="scss">
// youtube__wrap
.youtube__inner {
  .youtube__header {
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
  .youtube__body {
    padding-left: calc((100% - 1280px) / 2);

    .youtube__item {
      display: flex;
      gap: 10px;

      > div {
        width: 25%;

        img {
          width: 100%;
          border-radius: 20px;
        }
      }
    }
  }
}

// youtube__page
</style>

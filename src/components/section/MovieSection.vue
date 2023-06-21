<template>
  <section id="movieSection" :class="attr">
    <div class="movie__inner">
      <div class="movie__header container">
        <h3>주간 시집 추천</h3>
        <p>
          시요일의 시선이 닿은 곳.
          <br />
        </p>
        <a href="/" class="button-red"> 자세히 보기 </a>
      </div>
      <div class="movie__body">
        <div class="movie__item">
          <div>
            <img src="@/assets/images/movie/book01.png" alt="시집" />
          </div>
          <div>
            <img src="@/assets/images/movie/book02.png" alt="시집" />
          </div>
          <div>
            <img src="@/assets/images/movie/book03.png" alt="시집" />
          </div>
          <div>
            <img src="@/assets/images/movie/book04.png" alt="시집" />
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
  .movie__body {
    padding-left: calc((100% - 1280px) / 2);

    .movie__item {
      display: flex;
      gap: 20px;

      > div {
        width: 16%;

        img {
          width: 100%;
          border-radius: 20px;
        }
      }
    }
  }
}

//movie__cont
.movie__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    li {
      width: 24%;
      margin-bottom: 2%;
      position: relative;
      .title {
        display: inline-block;
        padding: 5px 0;
        font-size: 20px;
        font-weight: bold;
        &:hover {
          text-decoration: underline;
          text-underline-position: under;
        }
      }
      .star {
        position: absolute;
        right: 20px;
        top: 20px;
        width: 30px;
        height: 30px;
        background-color: #fff;
        text-align: center;
        line-height: 30px;
        border-radius: 50%;
        font-size: 12px;
      }
    }
  }
}

//movie__search
.movie__search {
  text-align: center;
  margin-bottom: 50px;
  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    border-radius: 50px;
    min-width: 300px;
    margin-right: 10px;
  }
  button {
    @include button(#4857ec, #fff);
    border-radius: 50px;
  }
}
</style>

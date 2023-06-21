<template>
  <section id="unsplashSection" :class="attr">
    <div class="unsplash__inner">
      <div class="unsplash__header container">
        <h3>시요일 기획</h3>
        <p>
          문학의
          <br />
          모든 고민
        </p>
        <a href="/" class="button-blue"> 자세히 보기 </a>
      </div>
      <div class="unsplash__body">
        <div class="unsplash__item">
          <div>
            <img src="@/assets/images/unsplash/unsplash01.png" alt="기획" />
          </div>
          <div>
            <img src="@/assets/images/unsplash/unsplash02.png" alt="기획" />
          </div>
          <div>
            <img src="@/assets/images/unsplash/unsplash03.png" alt="기획" />
          </div>
          <div>
            <img src="@/assets/images/unsplash/unsplash04.png" alt="기획" />
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
  .unsplash__body {
    padding-left: calc((100% - 1280px) / 2);

    .unsplash__item {
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

// unsplash__page
.unsplash__cont {
  ul {
    column-count: 4;
    li {
      margin-bottom: 20px;
    }
  }
}

//unsplash__search
.unsplash__search {
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

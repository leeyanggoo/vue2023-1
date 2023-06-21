<template>
  <section id="memberSection" :class="attr">
    <h3>오늘의 시인</h3>
    <p>펜촉이 잉크로 촉촉한 시인들을 소개합니다.</p>

    <div class="member__inner container">
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/peep-1.svg" alt="멤버" />
        </figure>
        <div class="member__body">
          <h4>김덕배</h4>
          <a href="/" class="btn"> 작품 보기 </a>
        </div>
      </div>
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/peep-2.svg" alt="멤버" />
        </figure>
        <div class="member__body">
          <h4>김덕배</h4>
          <a href="/" class="btn"> 작품 보기 </a>
        </div>
      </div>
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/peep-3.svg" alt="멤버" />
        </figure>
        <div class="member__body">
          <h4>김덕배</h4>
          <a href="/" class="btn"> 작품 보기 </a>
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
// members__wrap
.member__inner {
  @include flex-between;

  .member {
    width: 32%;
    border: 2px solid var(--color_body);

    .member__header {
      img {
        width: 100%;
      }
    }
    .member__body {
      margin-top: -90px;
      position: relative;
      padding: 15px 10px;
      background-color: #000;
      color: #fff;

      > h4 {
        font-size: 22px;
      }

      > a {
        color: #fff;
        text-decoration: underline;
        text-underline-position: under;
      }
    }
  }
}
</style>

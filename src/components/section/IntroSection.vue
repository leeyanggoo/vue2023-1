<template>
  <section id="introSection" :class="attr">
    <h3 class="blind">시요일 소개</h3>
    <div class="intro__inner container">
      <div class="intro__title">
        <span>we are</span>
        <h3 v-html="title"></h3>
        <p v-html="desc"></p>
      </div>
      <div class="intro__desc">
        <div v-for="(text, index) in texts" v-bind:key="index">
          <h4 :class="text.icon">{{ text.title }}</h4>
          <p>{{ text.desc }}</p>
        </div>
        <!-- <div>
          <h4 class="icon-book">43,000여편의 시</h4>
          <p>
            7개 출판사가 참여하여 고시조부터 현대대표시·창비시선·동시 등을 모두
            담은 앱
          </p>
        </div>
        <div>
          <h4 class="icon-hand">차별화된 큐레이션</h4>
          <p>시인들이 직접 엄선한 시를 배달하고 추천하는 큐레이션 기능</p>
        </div>
        <div>
          <h4 class="icon-search">강력한 검색 기능</h4>
          <p>본문·시어·시인·태그(주제어)를 이용한 빠르고 강력한 검색</p>
        </div>
        <div>
          <h4 class="icon-pencil">시作!일기</h4>
          <p>당신의 시를 남겨보세요!</p>
        </div> -->
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: {
    attr: String,
  },
  data: function () {
    return {
      title: `시요일?<br />`,
      desc: `시요일은 시요일은 최초·최대의<br />시詩큐레이션 검색 서비스입니다.`,
      texts: [
        {
          title: "43,000여편의 시",
          desc: "7개 출판사가 참여하여 고시조부터 현대대표시·창비시선·동시 등을 모두 담은 앱",
          icon: "icon-book",
        },
        {
          title: "차별화된 큐레이션",
          desc: "시인들이 직접 엄선한 시를 배달하고 추천하는 큐레이션 기능",
          icon: "icon-hand",
        },
        {
          title: "강력한 검색 기능",
          desc: "본문·시어·시인·태그(주제어)를 이용한 빠르고 강력한 검색",
          icon: "icon-search",
        },
        {
          title: "시作!일기",
          desc: "당신의 시를 남겨보세요!",
          icon: "icon-pencil",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
// intro__wrap
.intro__inner {
  display: flex;
  justify-content: space-between;
}
.intro__title {
  width: 33%;
  span {
    background-color: #ff3344;
    font-size: 14px;
    padding: 4px 30px 2px;
    color: #fff;
    border-radius: 40px;
    text-transform: uppercase;
    margin-bottom: 10px;
    display: inline-block;
  }
  h3 {
    font-size: 50px;
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 30px;
  }
  p {
    font-size: 18px;
    line-height: 1.5;
    font-weight: 500;
  }
}
.intro__desc {
  width: 66%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  > div {
    width: 48%;
    margin-bottom: 40px;
    h4 {
      display: inline-block;
      font-size: 24px;
      margin-bottom: 15px;
      font-weight: 500;
    }
    &:nth-child(3),
    &:nth-child(4) {
      margin-bottom: 0;
    }
  }
}
</style>

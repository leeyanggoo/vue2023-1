<template>
  <div class="intro__cont container">
    <div class="cont__box">
      <ul>
        <li v-for="(cont, index) in conts" :key="index">
          <img :src="cont.img" :alt="cont.title" />
          <h3>{{ cont.title }}</h3>
          <em>{{ cont.desc }}</em>
        </li>
      </ul>
    </div>
  </div>
</template>

<styel lang="scss">
// intro__cont
.intro__cont {
  margin: -100px auto 0;
  .cont__box {
    padding: 50px 0;
    ul {
      text-align: center;
      display: flex;
      flex-wrap: wrap;
      li {
        width: 33.3%;
        padding: 1em;
        margin-bottom: 1em;
        h3 {
          color: #1aa692;
          font-weight: 400;
          font-size: 1.5em;
          margin-bottom: 1em;
        }
        em {
          font-weight: 200;
          font-size: 1.3em;
        }
      }
    }
  }
}
</styel>
<script>
export default {
  data: function () {
    return {
      conts: [
        {
          img: "./assets/images/intro/device_1.png",
          title: "오늘의 시",
          desc: "하루 한 편, 무료 시 선물",
        },
        {
          img: "./assets/images/intro/device_2.png",
          title: "테마별 추천시",
          desc: "시요일이 엄선한 주제별 추천시",
        },
        {
          img: "./assets/images/intro/device_3.png",
          title: "검색",
          desc: "친절하고 강력한 검색 기능",
        },
        {
          img: "./assets/images/intro/device_4.png",
          title: "시요일의 선택",
          desc: "문화를 아우르는 다양한 시선",
        },
        {
          img: "./assets/images/intro/device_5.png",
          title: "선택 구절 공유",
          desc: "예쁜 이미지로 공유하는 시",
        },
        {
          img: "./assets/images/intro/device_6.png",
          title: "시낭송",
          desc: "시인의 음성으로 듣는 시",
        },
      ],
    };
  },
};
</script>

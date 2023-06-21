<template>
  <section id="portSection" :class="attr">
    <h3 v-html="title"></h3>
    <p>{{ desc }}</p>
    <div class="port__inner container">
      <div class="port__btn">
        <a href="/" class="active"> 月 </a>
        <a href="/">火</a>
        <a href="/">水</a>
        <a href="/">木</a>
        <a href="/">金</a>
        <a href="/">土</a>
        <a href="/">日</a>
      </div>
      <div class="port__cont">
        <div class="port" v-for="(text, index) in texts" :key="index">
          <figure class="port__header">
            <img :src="text.img" :alt="text.title" />
          </figure>
          <div class="port__body">
            <span>
              <img :src="text.member" :alt="text.author" />
            </span>
            <div>
              <h4>
                {{ text.author }} <em>{{ text.job }}</em>
              </h4>
              <p>{{ text.title }}</p>
            </div>
          </div>
        </div>
        <!-- <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/today01.png" alt="포트폴리오" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/member/peep-4.svg" alt="멤버" />
            </span>
            <div>
              <h4>김덕배 <em>시인</em></h4>
              <p>나의 밤은 당신의 낮보다 아름답다</p>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/today02.png" alt="포트폴리오" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/member/peep-5.svg" alt="멤버" />
            </span>
            <div>
              <h4>김덕배 <em>시인</em></h4>
              <p>잊혀진 도시의 목소리</p>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/today03.png" alt="포트폴리오" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/member/peep-6.svg" alt="멤버" />
            </span>
            <div>
              <h4>김덕배 <em>시인</em></h4>
              <p>별빛 아래, 그리움이 선물하는 것들</p>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/today04.png" alt="포트폴리오" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/member/peep-7.svg" alt="멤버" />
            </span>
            <div>
              <h4>김덕배 <em>시인</em></h4>
              <p>햇살이 부서진 그 곳에서</p>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/today05.png" alt="포트폴리오" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/member/peep-8.svg" alt="멤버" />
            </span>
            <div>
              <h4>김덕배 <em>시인</em></h4>
              <p>눈물로 쓰여진 희망의 노래</p>
            </div>
          </div>
        </div>
        <div class="port">
          <figure class="port__header">
            <img src="@/assets/images/port/today06.png" alt="포트폴리오" />
          </figure>
          <div class="port__body">
            <span>
              <img src="@/assets/images/member/peep-9.svg" alt="멤버" />
            </span>
            <div>
              <h4>김덕배 <em>시인</em></h4>
              <p>그대를 향한 미완성의 서정시</p>
            </div>
          </div>
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
      title: `오늘의 시<em>詩</em>`,
      desc: `당신을 위한 시詩 한 편`,
      texts: [
        {
          author: "김덕배",
          job: "시인",
          title: "나의 밤은 당신의 낮보다 아름답다",
          img: "./assets/images/port/today01.png",
          member: "./assets/images/member/peep-4.svg",
        },
        {
          author: "김덕배",
          job: "시인",
          title: "잊혀진 도시의 목소리",
          img: "./assets/images/port/today02.png",
          member: "./assets/images/member/peep-5.svg",
        },
        {
          author: "김덕배",
          job: "시인",
          title: "별빛 아래, 그리움이 선물하는 것들",
          img: "./assets/images/port/today03.png",
          member: "./assets/images/member/peep-6.svg",
        },
        {
          author: "김덕배",
          job: "시인",
          title: "햇살이 부서진 그 곳에서",
          img: "./assets/images/port/today04.png",
          member: "./assets/images/member/peep-7.svg",
        },
        {
          author: "김덕배",
          job: "시인",
          title: "눈물로 쓰여진 희망의 노래",
          img: "./assets/images/port/today05.png",
          member: "./assets/images/member/peep-8.svg",
        },
        {
          author: "김덕배",
          job: "시인",
          title: "그대를 향한 미완성의 서정시",
          img: "./assets/images/port/today06.png",
          member: "./assets/images/member/peep-9.svg",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
// ports__wrap
.port__wrap {
  > h3 {
    em {
      font-size: 40px;
      color: var(--color_gray);
    }
  }
}
.port__inner {
  .port__btn {
    margin-bottom: 50px;
    > a {
      padding: 10px 40px;
      background-color: var(--button_sky);
      border-radius: 50px;
      margin: 0 5px;
      font-size: 20px;

      &.active {
        background-color: var(--sky_border);
      }

      &:hover {
        box-shadow: 0 0 0 2px var(--color_main) inset;
      }
    }
  }
  .port__cont {
    @include flex-between;
    flex-wrap: wrap;

    .port {
      width: 32%;
      margin-bottom: 40px;

      .port__header {
        img {
          width: 100%;
          border-radius: 10px;
          margin-bottom: 20px;
          filter: grayscale(100%);
          transition: all 0.5s;
          &:hover {
            filter: grayscale(0%);
          }
        }
      }
      &:nth-child(1) span {
        background-color: #fd615b;
      }
      &:nth-child(2) span {
        background-color: #feda68;
      }
      &:nth-child(3) span {
        background-color: #d3cfea;
      }
      &:nth-child(4) span {
        background-color: #f3d2b3;
      }
      &:nth-child(5) span {
        background-color: #686a64;
      }
      &:nth-child(6) span {
        background-color: #817370;
      }
      .port__body {
        display: flex;
        span {
          display: block;
          width: 50px;
          height: 50px;
          border-radius: 50%;
          margin-right: 10px;
          overflow: hidden;
          img {
            transform: translate(-10%, 40%) scale(2.5);
          }
        }
        > div {
          text-align-last: left;
          h4 {
            font-size: 20px;
            font-weight: 700;

            em {
              font-size: 16px;
              color: var(--color_gray);
            }
          }
          p {
            font-size: 16px;
            font-weight: 500;
          }
        }
      }
    }
  }
}
</style>

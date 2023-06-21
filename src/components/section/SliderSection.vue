<template>
  <section id="sliderSection" :class="attr">
    <div class="slider__inner">
      <h2 class="blind">배너 슬라이드</h2>
      <div class="slider__img">
        <swiper
          :loop="true"
          :modules="modules"
          :slides-per-view="1"
          :speed="1000"
          navigation
          :pagination="{ clickable: true }"
          @swiper="onSwiper"
          @slideChange="onSlideChange"
          :autoplay="{
            delay: 2000,
            disableOnInteraction: false,
          }"
        >
          <swiper-slide
            class="bg-gradient"
            v-for="(slider, index) in sliders"
            :key="index"
          >
            <div class="slider s1 container">
              <div class="text">
                <h3 v-html="slider.title"></h3>
                <p v-html="slider.desc"></p>
                <a href="#" class="more button-blue">더 알아보기</a>
              </div>
              <div class="img">
                <img
                  src="@/assets/images/slider/littleprince.png"
                  alt="어린왕자"
                />
              </div>
              <div class="circle" aria-label="hidden">
                <span class="circle c1"></span>
                <span class="circle c2"></span>
                <span class="circle c3"></span>
                <span class="circle c4"></span>
                <span class="circle c5"></span>
              </div>
            </div>
          </swiper-slide>
        </swiper>
      </div>
      <div class="slider__btn">
        <a href="/" class="left">
          <span class="ir">이전 이미지</span>
        </a>
        <a href="/" class="right">
          <span class="ir">다음 이미지</span>
        </a>
      </div>
      <div class="slider__dot">
        <a href="/" class="dot active">
          <span class="ir">1번 이미지</span>
        </a>
        <a href="/" class="dot">
          <span class="ir">2번 이미지</span>
        </a>
        <a href="/" class="dot">
          <span class="ir">3번 이미지</span>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import { Navigation, Pagination, Autoplay } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

export default {
  props: {
    attr: String,
  },
  data: function () {
    return {
      sliders: [
        {
          title:
            "너의 장미꽃이 그토록 소중한 것은<br />그 꽃을 위해 네가 공들인 그 시간 때문이야.",
          desc: "우리가 아직도 어린왕자를 찾아가는 이유<br /><em>김덕배</em> 시인과 함께 알아보는 시간",
        },
        {
          title:
            "너의 장미꽃이 그토록 소중한 것은<br />그 꽃을 위해 네가 공들인 그 시간 때문이야.",
          desc: "우리가 아직도 어린왕자를 찾아가는 이유<br /><em>김덕배</em> 시인과 함께 알아보는 시간",
        },
        {
          title:
            "너의 장미꽃이 그토록 소중한 것은<br />그 꽃을 위해 네가 공들인 그 시간 때문이야.",
          desc: "우리가 아직도 어린왕자를 찾아가는 이유<br /><em>김덕배</em> 시인과 함께 알아보는 시간",
        },
      ],
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      onSwiper,
      onSlideChange,
      modules: [Navigation, Pagination, Autoplay],
    };
  },
};
</script>

<style lang="scss">
// slider__wrap
.slider__inner {
  position: relative;
  .slider__img {
    .slider {
      &.s1 {
        padding: 120px 0;
        .img {
          position: absolute;
          right: 0;
          top: 0;
          width: 600px;
          height: 600px;
          // z-index: -1;
        }
      }
      .text {
        h3 {
          font-size: 40px;
          font-weight: 800;
          text-transform: uppercase;
          line-height: 1.8;
          margin-bottom: 40px;
        }
        p {
          font-size: 24px;
          font-weight: 500;
          margin-bottom: 50px;
          em {
            font-weight: 800;
          }
        }
        .more {
          font-size: 18px;
        }
      }
      .circle {
        span {
          display: block;
          position: absolute;
          left: 50%;
          top: 50%;
          width: 20px;
          height: 20px;
          border-radius: 50%;
        }
        span:nth-child(1) {
          background-color: var(--button_blue);
          left: 30%;
          top: 80%;
          width: 10px;
          height: 10px;
        }
        span:nth-child(2) {
          background-color: var(--button_red);
          top: 10%;
          width: 40px;
          height: 40px;
        }
        span:nth-child(3) {
          background-color: var(--button_green);
          left: 100%;
          width: 30px;
          height: 30px;
        }
        span:nth-child(4) {
          background-color: var(--button_blue);
          left: 20%;
          top: -10%;
        }
        span:nth-child(5) {
          background-color: var(--button_green);
          left: -10%;
          top: 20%;
        }
      }
    }
  }
  .slider__btn {
    > a {
      position: absolute;
      width: 25px;
      height: 40px;
      top: 50%;
      background-repeat: no-repeat;
      background-position: center;
      transform: translateY(-50%);
      transition: opacity 0.3s;
      &:hover {
        opacity: 0.5;
      }
    }
    .left {
      left: 20px;
      background-image: url(@/assets/images/slider/sliderLeft.png);
    }
    .right {
      right: 20px;
      background-image: url(@/assets/images/slider/sliderRight.png);
    }
  }
  .slider__dot {
    position: absolute;
    left: 50%;
    bottom: 5%;
    transform: translateX(-50%);
    a {
      display: inline-block;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      margin: 0 5px;
      border: 4px solid #ff3344;
      background-color: #ff3344;
      box-shadow: 0 0 0 3px transparent;
      transition: all 0.3s;
      &.active {
        box-shadow: 0 0 0 3px #ff3344;
        border-width: 4px;
        background-color: #fff;
      }
      &:hover {
        transform: scale(1.2);
      }
    }
  }
}
</style>

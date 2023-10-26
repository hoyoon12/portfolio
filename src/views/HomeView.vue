<template>
  <v-app-bar app :color="appBarColor" elevation>
          <v-toolbar-title>YoonTfolio</v-toolbar-title>
          <v-btn class="text4" @click="scrollToabout">ABOUT</v-btn>
          <v-btn class="text4" @click="scrollToPortfolio">PORTFOLIIO</v-btn>
          <v-btn class="text4" @click="scrollTocontact">CONTACT</v-btn>
          </v-app-bar>
  
    
    <div id="top" style="background-image: url('/portfolio/backhoyoon.jpg');
     background-size: cover;
     text-align: center;
     background-attachment: scroll; 
     display: flex; 
     flex-direction: column; 
     justify-content: center;
     height: 130vh;">
       <div class="overlay">
          <p style="font-size: 400%; border: 2px  black; padding: 10px; font-family: Arial, sans-serif; color: white; ">HOYOON'S</p>
          <p style="font-size: 400%; border: 2px  black; padding: 10px; font-family: Arial, sans-serif; color: white; ">PORTFOLIO</p>
        </div>
     </div>
     

      <div id="about">
  <div class="container">
      <div class="image-container">
        <img src="/portfolio/hoyoon2.jpg" alt="My Image" />
      </div>
      <div class="description">
        <p>이름 : 나호윤</p>
        <p>나이 : 25살</p>
        <p>학력 : 명지전문대학 4년제</p>
        <p>학과 : 정보통신공학과</p>
        <p>거주지 : 서울 성북구 길음동 동부센트레빌아파트</p>
        <h2 style="margin-top: 5%; color: chartreuse;">#나호윤   #졸업프로젝트   #우리팀   #화이팅★</h2>
        <h2 style="color: aquamarine;">#javascript     #vue.js     #react     #node.js</h2>
      </div>
    </div>

          </div>
      


        


    <div id="portfolio">
      <div class="header">PORTFOLIO</div>

      <div class="list">
        <div class="item" @click="movePage('/portfolio1')" data-aos="zoom-out-down" data-aos-duration="3000"
          style="background-image: url(/portfolio/main.png)">
          <div class="item-content">
                  <h3 class="item-title">Develop Site</h3>
                  <p class="item-description">
                    개발자 사이트를 개발하여 프로젝트와 포트폴리오를 공유할 수 있고, AI가 추천해주는 주제를 이용해서 과업을 수행할 수 있다.
                  </p>
                </div>
        </div>
        <div class="item" data-aos="zoom-out-down" data-aos-duration="3000"
          style="background-image: url(/portfolio/pingpong.png)">
          <div class="item-content">
                    <h3 class="item-title">Pingpong</h3>
                    <p class="item-description">
                      코로나 기간동안 즐길 수 있는 실내스포츠로 아두이노우노와 파이어베이스를 결합시켜 만든 게임 시스템 구축
                    </p>
                  </div>
        </div>
        <div class="item" data-aos="zoom-out-down" data-aos-duration="3000"
          style="background-image: url(/portfolio/busbus.jpg)">
          <div class="item-content">
                    <h3 class="item-title">장애인 버스 시스템</h3>
                    <p class="item-description">
                      시각장애인 및 장애인들을 위한 대중교통 편의 시스템, 버스를 이용하는 장애인의 환경 개선
                    </p>
                  </div>
        </div>
        <div class="item" data-aos="zoom-out-down" data-aos-duration="3000"
          style="background-image: url(/portfolio/hak.jpg)">
          <div class="item-content">
                    <h3 class="item-title">정보통신공학과 학생회</h3>
                    <p class="item-description">
                      정보통신공학과 학생회의 축제주점 때 다같이 찍은 단체사진이다.
                    </p>
                  </div>
        </div>
        <div class="item" data-aos="zoom-out-down" data-aos-duration="3000"
          style="background-image: url(/portfolio/ch1.jpg)">
          <div class="item-content">
                    <h3 class="item-title">헬리오스 응원단</h3>
                    <p class="item-description">
                      정보통신공학과의 자랑 응원단 헬리오스. 2018,2019년도 2년연속 대상수상의 영광이 있다.
                    </p>
                  </div>
        </div>
        <div class="item" data-aos="zoom-out-down" data-aos-duration="3000"
          style="background-image: url(/portfolio/gg.jpg)">
          <div class="item-content">
                    <h3 class="item-title">고생하셨슴다</h3>
                    <p class="item-description">
                     남은 졸업프로젝트도 화이팅!!
                    </p>
                  </div>
        </div>
      </div>

    </div> 

   <div id="contact">
    <div class="container1">
      <div class="text-container1">
        <div class="description1">
          <h1>Contact</h1>
          <p>phone : 010-9306-2290</p>
          <p>email : yhn0236@naver.com</p>
          <p>address : seoul, sungbuk-gu , Gireum-dong</p>

        </div>
      </div>
      <div class="image-container1">
        <img src="/portfolio/jump.jpg" alt="Your Image" class="rounded-image" style= "max-height: 550px; margin-bottom: 50px;" />
      </div>
    </div>

      </div>

    

</template>

<script>
import { defineComponent } from 'vue';

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';
import aos from "aos";

// Components
import HelloWorld from '../components/HelloWorld.vue';

export default defineComponent({
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log('slide change');
    };
    return {
      onSwiper,
      onSlideChange,
    };
  },
  mounted() {
    aos.init();
  },

  methods: {

      scrollToabout() {
        const aboutSection = document.getElementById('about');
        if (aboutSection) {
          window.scrollTo({
            top: aboutSection.offsetTop,
            behavior: 'smooth',
          });
        }
      }
    ,
   scrollToPortfolio() {
      const portfolioSection = document.getElementById('portfolio');
      if (portfolioSection) {
        window.scrollTo({
          top: portfolioSection.offsetTop,
          behavior: 'smooth',
        });
      }
    }

    ,
    scrollTocontact() {
      const contactSection = document.getElementById('contact');
      if (portfolioSection) {
        window.scrollTo({
          top: contactSection.offsetTop,
          behavior: 'smooth',
        });
      }
    }

    ,

    movePage(path) {
      this.$router.push(path);
    }
  },

  name: 'HomeView',
});
</script>
<style lang="less">





.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.image-container {
  flex: 1;
  text-align: center;
}

.image-container img {
  max-width: 100%; /* 이미지의 최대 너비 설정 */
  height: 600px; /* 이미지의 높이 자동 조절 */
  border-radius: 10%;
}
.description {
  flex: 1;
  text-align: left; /* 텍스트를 왼쪽으로 정렬 */
  padding: 20px; /* 텍스트 주위의 공간 설정 */
  margin-bottom: 7%;
  font-family: Arial, sans-serif; /* 원하는 폰트 설정 */
  font-size: 20px; /* 원하는 폰트 크기 설정 */
  line-height: 200%;
}

.overlay {
  position: relative;
}

.overlay::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5); /* 원하는 배경색 또는 투명도 설정 */
  z-index: -1;
}

#about{
  position: relative;
  width: 100%;
  height: 960px;
    }


#top {

  height: 130vh;
  background-attachment: fixed;
  .headerfont{
  margin-top: 100px;
  }
}

#portfolio {
  .header {
    text-align: center;
    font-size: 40px;
  }

  width: 1000px;
  margin: 0 auto;

  .list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 30px;

    .item {
      width: 100%;

      background-position: center center;
      background-size: cover;
      aspect-ratio: 1/1;
      border-radius: 10%;
      //비율 1:1 비율이 되도록
      &:hover {
        transform: scale(1.1);

        .item-content {
          opacity: 1;
        }
      }

      .item-content {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        padding: 20px;
        background-color: rgba(0, 0, 0, 0.7);
        border-bottom-left-radius: 10px;
        border-bottom-right-radius: 10px;
        color: #fff;
        opacity: 0;
        transition: opacity 0.3s ease;

      }

      .item-title {
        font-size: 18px;
        font-weight: bold;
        margin-bottom: 10px;
      }

      .item-description {
        font-size: 14px;
      }
    }
  

  }


}
.container1 {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  max-width: 100%;
}

.text-container1 {
  flex: 1;
  text-align: center;
  padding: 30px;
  margin-top: 10%;
  font-family: Arial, sans-serif;
}

.image-container1 {
  flex: 1;
  text-align: center;
  height: 300px;
}

.rounded-image1 {
  max-width: 100%;
  height: auto;
  border-radius: 50%;
}

</style>

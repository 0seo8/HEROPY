<template>
  <section class="swiper">
    <Carousel
      :autoplay="5000"
      :wrap-around="true">
      <Slide
        v-for="slide in 5"
        :key="slide"
        class="slide">
        <div class="slide-area">
          <div
            :style="{backgroundImage: `url(/assets/swiper${slide}.png)`}"
            class="img">
          </div>
        </div>
      </Slide>

      <template #addons>
        <Pagination />
      </template>
    </Carousel>
  </section>

  <div class="textbox">
    <div class="textbox-img">
      <img
        src="/assets/heropy1.png"
        alt="" />
    </div>
    <div class="textbox-content">
      <h3>강사님의 다음 수강생분들께..</h3>
      <p>
        첫 번째, 수업 열심히 들어주세요. 
      </p>
      <p>
        두 번째, 줌 화면은 절대로 세 번 이상 끄지 마세요. 마음속으로 눈물 흘리시거든요.
      </p>
      <p>
        세 번째, 강사님이 질문하시면 대답 잘 해주세요. 강사님 안보시는 것 같으면서도 다 보고 계십니다.
      </p>
      <p>네 번째, 가끔 이런저런 얘기 해주시는데, 좋은 얘기니까 꼭 새겨 들으시면 좋을 거에요. </p>
    </div>
  </div>
  <div class="textbox">
    <div class="textbox-img">
      <img
        src="/assets/heropy2.jpg"
        alt="" />
    </div>
    <div class="textbox-content">
      <p>
        그리고, 아 참, 한 번씩 수염을 기르시는데, 안 깎으시는게 아니라 기르시는 거니까
      </p>
      <p><u><strong> "오늘 면도 안하셨어요?" </strong> 같은 질문은 하지 말아주세요.</u> </p>
      <p>우리 강사님, 사소한 질문도 성심성의껏 잘 받아주시고, 수업 시간이 끝나도 학생들이 질문 할 거 없나, </p>
      <p>하나라도 더 받아주시려고 기다려주시는 참 된 선생님이세요.</p> 
      <p> 
        앞으로 이런 분 만나기 쉽지 않을 거라고 생각합니다
      </p>
      <p>
        여러분들이 박영웅 강사님 수업을 듣게 된다면 굉장히 <strong> 큰 행운</strong>이랍니다!!
      </p>
    </div>
  </div>
  <div class="textbox">
    <p class="center">
      마지막으로..강사님! 4개월 동안 수고 많으셨습니다 <br />
      다음에 만나서 밥이라도 한 끼 같이 하고 싶어요~~(밥 사주세요😁)
    </p>
  </div>
</template>
<script>
import { defineComponent } from 'vue'
import { Carousel, Pagination, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
  name: 'Autoplay',
  components: {
    Carousel,
    Slide,
    Pagination,
  },
  data() {
    return {
      settings: {
        itemsToshow: 1,
        snapAlign: 'center',
      },
    }
  },
})
</script>


<style lang="scss" scoped>
.temp {
  width: 100vw;
  height: 650px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid red;
}

.slide-area {
  display: flex;
  justify-content: center;
  width: 100%;
  height: 100%;
  position: relative;
  color: rgb(234, 233, 233);
  text-shadow: 1px 1px 1px black;
  .img {
    width: 100%;
    min-height: 300px;
    max-height: 700px;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;
    position: relative;
    flex-shrink: 0;
  }
}

.carousel__pagination {
  margin-bottom: 0;
}
  
.textbox {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 24px 24px;
  width: 100%;
  border: 2px solid #ebebeb;
  border-bottom: 2px solid #ebebeb;
  border-top: 2px dashed #ebebeb;
  box-sizing: border-box;
  background-color: #fff;
  position: relative;
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
  &:before {
    content: "";
    background-image: url('https://heropy.blog/css/images/scissors.png');
    background-position: 0 -22px;
    background-size: cover;
    display: block;
    width: 22px;
    height: 22px;
    position: absolute;
    top: -11px;
    left: 20px;
    }
  &:hover {
    border: 2px solid #e96900;
    border-top: 2px dashed #e96900;
    .textbox-img img{
     transform: scale(1.15);
    }
    & +.textbox::before {
    background-image: none;
    }
    &:before {
      background-position: 0 0;
    }
  }
  &:last-child:hover {
    border-bottom: 2px solid #e96900;
  }  
  h3 {
    padding-bottom: 0.5em;
    border-bottom: 1px solid #ebebeb;
  }
  &-img {
    flex-shrink: 0;
    width: 30%;
    float: left;
    margin: 0 2% 0 0;
    border: 1px solid #ebebeb;
    border-radius: 4px;
    box-sizing: border-box;
    background: url('https://heropy.blog/css/images/pattern.png') #fff;
    overflow: hidden;
    transition: .4s;
  }
  img {
    width: 100%;
    margin: 10px 0;
    transition: .8s;
  }
  &-content {
    flex-grow: 1;
  }

  p {
    padding: 0;
    margin: 0;
    &.center {
      text-align: center;
      font-size: 18px;
    }
  }
  
}
</style>

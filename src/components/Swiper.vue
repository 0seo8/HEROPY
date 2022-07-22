<template>
  <section class="swiper">
    <Carousel
      :autoplay="2000"
      :wrap-around="true">
      <Slide
        v-for="slide in 37"
        :key="slide"
        class="slide">
        <div class="slide-area">
          <div
            :style="{backgroundImage: `url(/assets/example${slide}.png)`}"
            class="img">
          </div>
        </div>
      </Slide>

      <template #addons>
        <Pagination />
      </template>
    </Carousel>
  </section>
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
  width: 100%;
  height: 100%;
  position: relative;
  color: rgb(234, 233, 233);
  text-shadow: 1px 1px 1px black;
  .img {
    width: 100%;
    height: 600px;
    background-size: cover;
    background-position: center;
    position: relative;
    flex-shrink: 0;
  }
}
</style>

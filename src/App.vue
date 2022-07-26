<template>
  <div class="container">
    <TheHeader />
    <RouterView />
  </div>
</template>

<script>
import TheHeader from '~/components/TheHeader.vue'
export default {
  components : {
    TheHeader,
  },

}
</script>

<style lang="scss">
*, *::after, *::before {
  box-sizing: content-box; 
}

a {
  text-decoration: none;
  display: block;
}

body {
  font-family: Lato, sans-serif;
  position: relative;
  height: 100%;
  margin: 0;
  color: var(--color-basic-text);
  font-size: 1em;
  line-height: 1.7;
  letter-spacing: .2px;
  background: url('https://heropy.blog/css/images/pattern.png');
}
#app {
  overflow: hidden;
}

.container {
  padding-top: 100px;
  padding-bottom: 24px;
  max-width: 1200px;
}

.swiper {
  padding-top: 16px;
  border: 2px solid #ebebeb;
  border-bottom: none;
  border-top: 2px solid #ebebeb;
  box-sizing: border-box;
  background-color: #fff;
  position: relative;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  border-bottom-left-radius: 10px;
  &:hover {
    border: 2px solid #e96900;
    border-top: 2px solid #e96900;
    border-bottom: none;
  }
}

.carousel__pagination-button {
  background-color: #fdb223 !important;
  &--active {
    background-color: #E96900 !important;

  }
}
</style>

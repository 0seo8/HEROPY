<template>
  <div class="container">
    <TheHeader />
    <TheNav />
    <RouterView />
  </div>
</template>

<script>
import TheHeader from '~/components/TheHeader.vue'
import TheNav from '~/components/TheNav.vue'
export default {
  components : {
    TheHeader,
    TheNav,
  }
}
</script>

<style>
body {
  font-family: 'Roboto', sans-serif;
}
  .container {
    margin-top: 3rem;
  }
</style>

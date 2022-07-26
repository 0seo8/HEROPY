<template>
  <header class="header">
    <div class="header-container">
      <RouterLink
        to="/"
        class="header__link">
        <h1 class="logo"></h1>
        <span>See You Again <br />Heropy!</span>
      </RouterLink>
      <div class="header-temp"></div>
      <ul class="header-icons">
        <li
          v-for="nav in navigations"
          :key="nav.name">
          <RouterLink
            :to="nav.href"
            class="nav-link"
            active-class="active">
            <span class="material-symbols-outlined">{{ nav.name }}</span>
          </RouterLink> 
        </li>
        <li>
          <a href="">
            <svg
              height="32"
              aria-hidden="true"
              viewBox="0 0 16 16"
              version="1.1"
              width="32"
              data-view-component="true"
              class="octicon octicon-mark-github v-align-middle">
              <path
                fill="#2f5e82"
                d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z" />
            </svg>
          </a>
        </li>
      </ul>
      <div id="scroll-location-display">
        <span>{{ scrollHeight }}%</span>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      navigations: [
        {
          name: 'mail',
          href: '/letters'
        },
        {
          name: 'slideshow',
          href: '/vedio'
        },
        {
          name: 'photo_library',
          href: '/msg'
        },
      ],
      timerId: null,
      scrollHeight:0
    }
  },
  mounted() {
  window.addEventListener('scroll', () => {
    this.throttle(this.onScroll, 100)
  })
  },
  methods: {
    throttle(callback, time) {
      if (this.timerId) return
      this.timerId = setTimeout(() => {
        callback()
        this.timerId = undefined
      }, time)
    },
    onScroll() {
      const scrollTop = document.documentElement.scrollTop
      const height =
      document.documentElement.scrollHeight -
      document.documentElement.clientHeight
      const scrollWidth = (scrollTop / height) * 100
      this.scrollHeight=Math.floor(scrollWidth)
    }
  },
}
</script>


<style lang="scss" scoped>
.header {
  background: rgba(255,255,255,.95);
  border: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 200;
  transition: background .5s;
  border-bottom: 2px solid #ebebeb;
  &-container {
    max-width: 1200px;
    height: 40px;
    margin: 0 auto;
    padding: 10px 40px;
    position: relative;
    display: flex;
  }
  &__link {
    margin-right: 30px;
    display: flex;
    align-items: center;
    float: left;
    font-weight: 700;
    font-size: 1em;
    line-height: 16px;
    letter-spacing: -.8px;
    color: #e96900;
    .logo {
      background: url('https://heropy.blog/css/images/logo.png') center/contain no-repeat;
      width: 40px;
      height: 40px;
      margin-right: 4px;
    }
  }
  &-temp {
    flex: 1;
    height: 40px;
    display: flex;
    align-items: center;
    line-height: 1.2;
    font-size: 14px;
    font-weight: 700;
  }
  &-icons {
    list-style: none;
    display: flex;
    align-items: center;
    padding: 0;
    margin: 0;
    li {
      height: 100%;
      cursor: pointer;
      opacity: .5;
      transition: .1s;
      padding: 0;
      margin: 0;
      .nav-link, a {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
        padding: 0 10px;
      }
    }
  }
}
  span:hover {
    color: #e96900
   }

li span {
  color: #2f5e82;
  font-size: 32px;
}

#scroll-location-display {
  position: fixed;
  top: 60px;
  left: 0;
  margin: 0 -2px -2px 0;
  padding: 2px 10px;
  background: #e96900;
  border: 2px solid #34495e;
  border-top: none;
  border-left: none;
  border-radius: 0 0 4px;
  color: #fff;
  font-size: 12px;
  font-weight: 900;
  cursor: default;
  transition: .4s;
  transform-origin: 0 0;
}
</style>

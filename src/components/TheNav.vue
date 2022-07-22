<template>
  <ul
    class="nav nav-pills">
    <li
      v-for="nav in navigations"
      :key="nav.name"
      class="nav-item p-2">
      <RouterLink
        :to="nav.href"
        class="nav-link"
        active-class="active">
        {{ nav.name }}  
      </RouterLink> 
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      navigations: [
        {
          name: 'Letters',
          href: '/letters'
        },
        {
          name: 'Gallery',
          href: '/gallery'
        },
        {
          name: 'Message',
          href: '/msg'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
 ul {
  display: flex;
  align-items: center;
  justify-content: center;
    li {
      text-align: center; 
      font-size: 2rem;
      flex-grow:1;
    }
 }
</style>

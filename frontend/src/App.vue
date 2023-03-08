<template>
  <Menu />
  <div class="container">
    <router-view/>
  </div>
</template>

<script>
import Menu from '@/components/Menu.vue'

export default {
  name: 'App',
  components: {
    Menu
  }
}
</script>


<style lang="scss">
.container {
  max-width: 500px;
  margin: 0 auto;
}
</style>

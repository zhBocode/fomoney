<template>
  <div id="app">
    <a-header></a-header>
    <router-view></router-view>
    <a-footer></a-footer>
  </div>
</template>

<script>
import aHeader from '@/components/header/header'
import aFooter from '@/components/footer/footer'
export default {
  name: 'app',
  components:{
      aHeader,
      aFooter
  }
}
</script>

<style>
#app{
  
}
</style>

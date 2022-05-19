<template>
  <div id="app">
    <HeaderComponent/>
    <MainComponent/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
export default {
  name: 'App',
  components: {
    MainComponent,
    HeaderComponent
  }
}
</script>

<style lang,
    HeaderComponent="scss">
@import './assets/style/general';
@import './assets/style/utils'
</style>

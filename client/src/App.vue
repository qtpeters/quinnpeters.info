<template>
  <div id="site-container">
    <Header />
    <div id="app">
      <router-view/>
    </div>
    <Footer />
  </div>
</template>

<script lang="ts">

  import { Component, Vue } from 'vue-property-decorator';
  import Header from '@/components/Header.vue';
  import Footer from '@/components/Footer.vue';

  @Component({
    components: {
      Header,
      Footer
    }
  })
  export default class App extends Vue {}
</script>

<style lang="scss">

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    border-top: 1px solid #1f1f1f;
    border-bottom: 1px solid #1f1f1f;
    background-color: #2d2d2d;
    background-image: -webkit-linear-gradient( top, #3d3d3d, #272727 );
    background-image: -ms-linear-gradient( top, #3d3d3d, #272727 );
    background-image: -moz-linear-gradient( top, #3d3d3d, #272727 );
    background-image: -o-linear-gradient( top, #3d3d3d, #272727 );
  }

  html,body {
    height: 100%;
    background-color: #424242;
    margin: 0;
    padding: 0;
    border: 0;
  }

  #site-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 100%;
  }

</style>

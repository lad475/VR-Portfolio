<template>
  <div id="app">
    <MyHeader v-on:pageChange="changePageName"/>
    <MainContainer v-bind:pageName="page"/>
    <MyFooter/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import MainContainer from './components/main-container.vue';
import MyFooter from './components/my-footer.vue';
import MyHeader from './components/my-header.vue';

@Component({
  components: {
    MainContainer,
    MyFooter,
    MyHeader,
  },
})
export default class App extends Vue {
  public page = 'home';

  public changePageName(val: string) {
    this.page = val;
  }
}
</script>

<style lang="scss">
@font-face {
  font-family: 'Girls Have Many Secrets';
  font-style: normal;
  font-weight: normal;
  src: url('./assets/fonts/Girls\ Have\ Many\ Secrets.ttf') format('truetype');
}

body {
  background-color: rgb(223, 225, 236);
  font-family: 'Girls Have Many Secrets', sans-serif;
  height: 100%;
  margin: 0;
  padding: 0;
}

#app {
  min-height: 100vh;
  position: relative;
}
</style>

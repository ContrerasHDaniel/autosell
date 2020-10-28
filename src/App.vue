<template>
  <v-app id="app">
    <router-view class="application-container"></router-view>
  </v-app>
</template>

<style lang="scss">
@import './styles/layout';

body{
  margin: 0;
  padding: 0;
  --application-primary-color: #fbfbf2;
  // --application-primary-color: #FCFFFD;
  --application-accent-color: #64b6ac;
  --application-accent-text-color: #DAFFEF;
  --application-text-color: #5d737e;
}

* {
  box-sizing: border-box;
}

#app {
  /* System Fonts as used by GitHub */
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
                Helvetica, Arial, sans-serif, "Apple Color Emoji",
                "Segoe UI Emoji", "Segoe UI Symbol";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>

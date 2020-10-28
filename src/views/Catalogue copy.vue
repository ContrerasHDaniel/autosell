<template>
  <v-app id="inspire">
    <v-main class="app-content">
      <v-navigation-drawer
        width="357"
        absolute
        permanent
      >
      </v-navigation-drawer>
      <v-content>
        <div>Here</div>
      </v-content>
    </v-main>
  </v-app>
</template>

<script>
export default {
  //
};
</script>

<style lang="scss" scoped>
.nav-search {
  margin-top: 0.5rem;
  font-weight: 400;
}

.theme--dark.v-label {
  color: red !important;
}

#navbar {
  background-color:  #64b6ac;
}

.app-content {
  display: flexbox;
  background-color: #FBFBF2;
}

.flex {
  margin: 0;
  margin-left: 360px;
  width: 100%;
  max-width: 100vh;
}

.catalogue {
  max-width: 100%;
}
</style>

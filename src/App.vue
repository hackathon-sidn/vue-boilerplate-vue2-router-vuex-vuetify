<template>
  <v-window>
    <v-app id="inspire">
      <v-app id="sandbox">
        <v-main>
          <NavigationBar title="Vue App"></NavigationBar>
          <router-view />
        </v-main>
      </v-app>
    </v-app>
  </v-window>
</template>

<script>
import NavigationBar from "./components/layout/NavigationBar.vue";

export default {
  name: "App",

  components: {
    NavigationBar,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
html,
body {
  /* remove scrollbar on desktop when not needed */
  overflow-y: auto !important;
}
</style>

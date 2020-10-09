<template>
  <div class="navbar">
    <v-navigation-drawer
      v-model="primaryDrawer.model"
      :clipped="primaryDrawer.clipped"
      :floating="primaryDrawer.floating"
      :mini-variant="primaryDrawer.mini"
      :permanent="primaryDrawer.type === 'permanent'"
      :temporary="primaryDrawer.type === 'temporary'"
      app
      overflow
    >
      <v-list>
        <v-list-item
          v-for="navItem in navBarList"
          :key="navItem.to"
          :to="navItem.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ navItem.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ navItem.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar id="app-bar" :clipped-left="primaryDrawer.clipped" app>
      <v-app-bar-nav-icon
        id="nav-icon"
        @click.stop="togglePrimaryDrawer"
      ></v-app-bar-nav-icon>

      <v-toolbar-title>{{ title }}</v-toolbar-title>

      <v-spacer></v-spacer>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: "NavigationBar",
  props: {
    title: String,
  },

  components: {},

  data: () => ({
    primaryDrawer: {
      model: false,
      type: "temporary",
      clipped: true,
      floating: false,
      mini: false,
    },
    navBarList: [
      {
        to: "/",
        icon: "mdi-home",
        title: "Home",
      },
      {
        to: "/about",
        icon: "mdi-information",
        title: "About",
      },
    ],
  }),
  methods: {
    togglePrimaryDrawer() {
      this.primaryDrawer.model = !this.primaryDrawer.model;
    },
  },
};
</script>

<style scoped>
#app-bar {
  background: #000;
  color: rgb(93, 188, 210);
}
#nav-icon {
  color: rgb(93, 188, 210);
}
</style>
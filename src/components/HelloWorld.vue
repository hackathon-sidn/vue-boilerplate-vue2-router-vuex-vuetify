<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.png')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">Vue App</h1>
      </v-col>

      <v-col class="mb-5" cols="12">
        <h2 class="headline font-weight-bold mb-3">Important Links</h2>

        <v-row justify="center">
          <a
            v-for="(link, i) in importantLinks"
            :key="i"
            :href="link.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ link.text }}
          </a>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",

  data: () => ({
    importantLinks: [
      {
        text: "Vue.js Guide",
        href: "https://vuejs.org/v2/guide/",
      },
      {
        text: "Vuetify UI Components",
        href: "https://vuetifyjs.com/en/components/application/",
      },
      {
        text: "Example App",
        href: "https://github.com/fancy-flashcard/ffc",
      },
    ],
  }),
};
</script>

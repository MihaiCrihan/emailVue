<template>
  <v-app>
    <div>
      <b-nav style="background-color: #e0e0e0">
        <b-img :src="require('./assets/logob.png')" fluid alt="logo"></b-img>
        <b-nav-item href="#1">Link 1</b-nav-item>
        <b-nav-item href="#2">Link 2</b-nav-item>
        <b-nav-text>Plain text</b-nav-text>
      </b-nav>
    </div>

    <v-content>
      <HelloWorld />
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld
  },

  data: () => ({
    //
  })
};
</script>

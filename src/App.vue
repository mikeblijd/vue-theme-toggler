<template>
  <div id="app" v-bind:class="currentTheme">
    <!-- {{ currentTheme }} --> <!-- Show what is currently in localStorage-->
    <h5 class="text-center title">(Light / Dark mode)</h5>
    <div class="content-box">
      <div class="theme-switcher-wrap">
        <div
          class="theme-switcher"
          v-on:click="switchTheme"
          v-bind:class="{'active': currentTheme === 'theme-dark'}"
        >
          <div class="switch-path">
            <div class="switch-handle"></div>
          </div>
        </div>
      </div>
      <h3>Custom Dark Theme Toggler</h3>
      <h5>(VUEJS. SCSS/CSS, Local Storage)</h5>
      <p>
        "Sed ut perspiciatis unde omnis iste natus error sit voluptatem
        accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab
        illo inventore veritatis et quasi architecto beatae vitae dicta sunt
        explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut
        odit aut fugit, sed quia consequuntur magni dolores eos qui ratione
        voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum
        quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam
        eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat
        voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam
        corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur?
        Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse
        quam nihil molestiae consequatur, vel illum qui dolorem eum fugiat quo
        voluptas nulla pariatur?"
      </p>
      <p>-- WEMEET --</p>
    </div>
  </div>
</template>


<script>
export default {
  name: "App",
  data() {
    return {
      currentTheme: localStorage.getItem("theme-color"),
    };
  },
  methods: {
    switchTheme() {
      // Logic
      const storedTheme = localStorage.getItem("theme-color");
      if (storedTheme === "theme-dark") {
        localStorage.setItem("theme-color", "theme-light");
        this.currentTheme = localStorage.getItem("theme-color");
      } else {
        localStorage.setItem("theme-color", "theme-dark");
        this.currentTheme = localStorage.getItem("theme-color");
      }
    },
  },
};
</script>


<style>
html {
  height: 100%;
}
body {
  margin: 0;
  padding: 0;
  height: 100%;
}
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
}
h5.title {
  font-size: 22px;
  margin: 0;
  padding: 20px 0 0 0;
}
@import "main.css";
</style>

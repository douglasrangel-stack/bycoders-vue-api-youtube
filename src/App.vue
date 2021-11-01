<template>
  <div id="app">
    <Header />
    <main class="main">
      <transition mode="out-in">
        <router-view />
      </transition>
    </main>
  </div>
</template>

<script>

import Header from "@/components/Header.vue";

export default {
  name: "App",
  components: {
    Header
  },
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@300;400;700&display=swap');

body {
  font-family: "Lato", sans-serif;
}

img {
    max-width: 100%;
    height: auto;
}

input,
select,
textarea {
    text-shadow: 0 0 0 transparent;
    box-shadow: 0 0 0 transparent;
    outline: none !important;
}

select {
    appearance: none;
}

* {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    outline: none !important;
}

a {
    transition: all ease-in-out 0.3s;
}

ul {
    padding: 0;
    margin: 0;
}

:focus {
    outline: none;
}

.aligh-div-center {
    display: flex;
    align-items: center;
    justify-content: center;
}

.row {
    display: flex;
    flex-wrap: wrap;
    margin-right: -15px;
    margin-left: -15px;
}

.col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10 {
    position: relative;
    width: 100%;
    padding-right: 15px;
    padding-left: 15px;
    box-sizing: border-box;
}

.col-2, .col-3, .col-4, .col-5, .col-6, .col-7, .col-8, .col-9, .col-10 {
  position: relative;
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
  box-sizing: border-box;
}

.col-3 {
    flex: 0 0 25%;
    max-width: 25%;
}

.col-9 {
    flex: 0 0 75%;
    max-width: 75%;
}

@media (min-width: 768px) {
  .col-md-2 {
      flex: 0 0 16.666667%;
      max-width: 16.666667%;
  }
  .col-md-3 {
      flex: 0 0 25%;
      max-width: 25%;
  }
  .col-md-4 {
      flex: 0 0 33.333333%;
      max-width: 33.333333%;
  }
  .col-md-5 {
      flex: 0 0 41.666667%;
      max-width: 41.666667%;
  }
  .col-md-6 {
      flex: 0 0 50%;
      max-width: 50%;
  }
  .col-md-7 {
      flex: 0 0 58.333333%;
      max-width: 58.333333%;
  }
  .col-md-8 {
      flex: 0 0 66.666667%;
      max-width: 66.666667%;
  }
  .col-md-9 {
      flex: 0 0 75%;
      max-width: 75%;
  }
  .col-md-10 {
      flex: 0 0 83.333333%;
      max-width: 83.333333%;
  }
}

.col-mb {
  margin-bottom: 10px;
}

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
}

.container {
  width: 1440px;
  max-width: 100%;
  margin: 0 auto;
}

.line_flex {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
}

.d-none {
  display: none !important;
  width: 0;
  height: 0;
  opacity: 0;
}
</style>

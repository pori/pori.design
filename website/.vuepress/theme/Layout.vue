<template>
  <div>
    <template v-if="$route.path === '/'">
      <div class="container">
        <Homepage/>
      </div>
      <Rainbow/>
    </template>
    <div v-else class="container">
      <Content/>

      <div class="cute-footer">
        <img src="/alex-hernandez.png" alt="Alex Hernandez">
      </div>
    </div>
  </div>
</template>

<script>
import Homepage from "./Homepage.vue";
import Rainbow from "./Rainbow.vue";

export default {
  components: {
    Homepage,
    Rainbow
  }
};
</script>

<style lang="scss">
:root {
  /* Color */
  --primary: #ff91af;
  --secondary: #8bd5e9;
  --black: #804957;
  --grey: #806F73;
  --muted: #e0e0e0;
  --bg: #FFDEE7;

  /* Type */
  --heading-typeface: "Libre Baskerville", serif;
  --body-typeface: "Libre Franklin", sans-serif;
  --type-scale: 1.125rem;

  /* Globals */
  --border-radius: 3px;
}

*,
*:before,
*:after {
  box-sizing: border-box;
}

html,
body {
  font-size: var(--type-scale);
  margin: 0;
}

body {
  background-color: var(--bg);
  font-family: var(--heading-typeface);
  font-weight: 400;
  line-height: 1.45;
  color: #333;
}

p {
  font-family: var(--body-typeface);
  margin-bottom: 1.3em;
  color: var(--black);
}

h1,
h2,
h3,
h4 {
  margin: 1.414em 0 0.5em;
  font-weight: bold;
  line-height: 1.2;
  color: var(--black);
}

h1 {
  margin-top: 0;
  font-size: calc(var(--type-scale) * 4);
}

h2 {
  font-size: calc(var(--type-scale) * 3);
  // word-break: break-all;
}

h3 {
  font-size: calc(var(--type-scale) * 2);
  font-weight: lighter;
}

h4 {
  font-size: var(--type-scale);
  font-weight: lighter;
}

small {
  font-size: 0.618em;
}

section {
  margin-bottom: 5rem;

  &:first-child {
    margin-top: 5rem;
  }
}

a {
  color: var(--primary);
  text-decoration: none;
  font-weight: bold;
  transition: color 0.3s;

  &:hover {
    color: var(--secondary);
  }
}

.button {
  background: var(--primary);
  padding: 1rem 1.5rem;
  color: white !important;
  font-family: var(--body-typeface);
  border-radius: var(--border-radius);
  font-weight: bold;
  transition: all 0.5s !important;

  &:hover {
    background: var(--secondary);
    box-shadow: 0 4px 4px rgba(0, 0, 0, 0.5);
    transition: all 0.3s;
  }
}

.container {
  width: 1000px;
  margin: 0 auto;
}

.cute-footer {
  text-align: center;

  img {
    z-index: -1000;
    position: fixed;
    margin: 0 auto;
    left: 0;
    right: 0;
    bottom: -100px;
    margin: 0 auto;
    width: 200px;
    transition: bottom 1s;

    &:hover,
    &:active {
      bottom: -50px;
    }
  }
}

@media (max-width: 1024px) {
  h2,
  h3 {
    font-size: xx-large;
  }

  .container {
    width: 100%;
    padding-left: 1em;
    padding-right: 1em;
  }
}
</style>
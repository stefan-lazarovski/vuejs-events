<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div id="layout">
    <header>
      <div class="wrapper">
        <nav>
          <RouterLink :to="{name: 'event-list'}">Events</RouterLink> |
          <RouterLink :to="{name: 'about'}">About</RouterLink>
        </nav>
      </div>
    </header>
    <RouterView />
  </div>
</template>

<style lang="scss">
:root {
  --dark: #212219;
}
.text-secondary {
  color: #999;
}
#layout {
  font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: var(--dark);
  font-weight: normal;
  line-height: 1.3;
}
h1, h2, h3, h4, h5, h6 {
  line-height: 1;
}
.text-center {
  text-align: center;
}
header {
  line-height: 1.5;
  max-height: 100vh;
  margin-bottom: max(2rem, 2vw);
}

nav {
  width: 100%;
  font-size: 15px;
  text-align: center;
  margin-top: 2rem;

  a {
    text-decoration: none;
    position: relative;
    color: var(--dark);
    padding: 0.5rem;

    &::after {
      content: "";
      display: block;
      position: absolute;
      bottom: 0;
      left: 0;
      width: 0;
      height: 1px;
      background-color: var(--dark);
      transition: .3s all ease-in-out;
    }

    &:hover {
      &::after {
        width: 100%;
      }
    }
  }
}

// nav a.router-link-exact-active {
//   color: var(--color-text);
// }

// nav a.router-link-exact-active:hover {
//   background-color: transparent;
// }
</style>

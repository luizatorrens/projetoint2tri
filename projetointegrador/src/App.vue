<script setup>
import HeaderComp from "./components/HeaderComp.vue";
import FooterComp from "./components/FooterComp.vue";
</script>
<template>
  <HeaderComp />
  <main>
    <RouterView />
  </main>
  <FooterComp />
</template>

<style>
@import "@/assets/base.css";
@import "@/assets/style.css";

#app {
  max-width: 1280px;
  margin: 0 auto;
  height: 100vh;

  font-weight: normal;
}
header {
  background-color: rgb(255, 135, 135);
  color: white;
  height: 15%;
  font-size: 1.3rem;
  display: flex;
}
footer {
  background-color: rgb(255, 135, 135);
  color: rgb(29, 29, 173);
  height: 5%;
  font-size: 1.3rem;
}
main {
  height: 80%;
  background-color: white;
  color: black;
}
a {
  text-decoration: none;
  color: inherit;
}
</style>

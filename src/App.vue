<script setup>
import HeaderComp from "@/components/template/HeaderComp.vue";
</script>

<template>
  <HeaderComp />
  <RouterView />
</template>

<style>
@import "@/assets/base.css";

#app {
  max-width: 1300px;
  margin: 0 auto;
  height: 110vh;
  font-weight: normal;
}

a {
  color: inherit;
  text-decoration: none;
}

footer {
  height: 10%;
  background-color: rgb(70, 44, 143);
  color: white;
  font-size: 1.3rem;
  display: flex;
  align-items: center;
  padding-left: 20px;
}

header span {
  padding: 0 20px;
}

main {
  height: 70%;
  background-color: rgb(180, 56, 238);
}
</style>

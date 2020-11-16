<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">index</router-link> |
      <!-- <router-link to="/layout">layout1</router-link> |
      <router-link to="/layout_2">layout2</router-link> |
      <router-link to="/layout_3">layout3</router-link> -->
    </div>
    <router-view :key="$route.path" />
  </div>
</template>

<style lang="scss">
// @import '../assets/scss/app.scss';
@import './assets/scss/app.scss'
</style>

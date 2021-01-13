<template>
  <div id="app" class="app container-fluid">
    <div id="nav">
      <!-- <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link> -->
    </div>
      <vue-page-transition name="fade-in-up">
        <router-view />
      </vue-page-transition>
  </div>
</template>

<style>
  @import './css/style.css';
  @import './css/vueBirthDatepicker.css';
  
</style>

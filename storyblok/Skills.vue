<template>
    <section class="skills__section">
      <div class="skill__item">
        <h2>{{ blok.title1 }}</h2>
        <p>{{ blok.text1 }}</p>
      </div>
      <div class="skill__item">
        <h2>{{ blok.title2 }}</h2>
        <p>{{ blok.text2 }}</p>
      </div>
      <div class="skill__item">
        <h2>{{ blok.title3 }}</h2>
        <p>{{ blok.text3 }}</p>
      </div>
      <div class="skill__item">
        <h2>{{ blok.title4 }}</h2>
        <p>{{ blok.text4 }}</p>
      </div>
      <div class="skill__item">
        <h2>{{ blok.title5 }}</h2>
        <p>{{ blok.text5 }}</p>
      </div>
      <div class="skill__item">
        <h2>{{ blok.title6 }}</h2>
        <p>{{ blok.text6 }}</p>
      </div>
    </section>
  </template>
  
  <script setup>
  defineProps({ blok: Object })
  </script>
  
  <style lang="scss" scoped>
  .skills__section {
    overflow-x: hidden;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    padding: 50px 0px 80px 0px;
    grid-row-gap: 60px;
    @media only screen and (max-width: $tablet) {
        grid-template-columns: 1fr 1fr;
    }
    @media only screen and (max-width: $mobile) {
        grid-template-columns: 1fr;
        justify-items: center;
        text-align: center;
    }
  }
  
  h2 {
    @include font-l;
  }
  </style>
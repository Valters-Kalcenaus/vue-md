<template>
    <div class="navigation">
      <button @click="navigate('home')" :class="{ active: current === 'home' }">HOME</button>
      <button @click="navigate('about')" :class="{ active: current === 'about' }">ABOUT ME</button>
    </div>
  </template>



  <script>  
  import HomeComponent from './HomeComponent.vue';
  import AboutMeComponent from './AboutMeComponent.vue';
  export default {
    data() {
      return {
        current: 'home'
      };
    },
    methods: {
      navigate(page) {
        this.current = page;
        this.$emit('navigate', page === 'home' ? HomeComponent : AboutMeComponent);
      }
    }
  };

  </script>
  
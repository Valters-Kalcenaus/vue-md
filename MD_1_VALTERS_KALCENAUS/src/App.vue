<template>
  <div> 
    <HeaderComponent @login="showContent" @logout="hideContent" />
    <div class="Page" v-if="loggedIn">
      <div class="NavBox">
        <NavigationComponent @navigate="changePage" />
      </div>
      <div class="content">
        <component :is="currentPage" />
      </div>
    </div>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import NavigationComponent from './components/NavigationComponent.vue';
import HomeComponent from './components/HomeComponent.vue';
import AboutMeComponent from './components/AboutMeComponent.vue';

export default {
  components: {
    HeaderComponent,
    NavigationComponent,
    HomeComponent,
    AboutMeComponent
  },
  data() {
    return {
      loggedIn: false,
      currentPage: HomeComponent
    };
  },
  methods: {
    showContent() {
      this.loggedIn = true;
    },
    hideContent() {
      this.loggedIn = false;
    },
    changePage(page) {
      this.currentPage = page;
    }
  }
};
</script>

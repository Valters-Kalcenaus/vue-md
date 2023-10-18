<template>
  <div class="header-bar" :style="{ backgroundColor: loggedIn ? userColor : defaultColor }">
    <div class="obj-container">
      
      <img src="@/assets/logo(white).svg" alt="Logo" class="logo"/>

      <H2>KRAKEN.FM</H2>

    </div>
    <div class="obj-container">
      <div class="user-info" v-if="loggedIn">
        <div class="obj-container UserText">
        <img class="avatar" :style="{ backgroundColor: randomColor() }" src="@/assets/logo.png"/>
        {{ fullName }}
        </div>
        
      </div>
      <button @click="toggleLogin" class="button" :style="{ backgroundColor: loggedIn ? defaultColor : userColor }">
        {{ loggedIn ? 'LOGOUT' : 'LOGIN' }}
      </button>
    </div>
  </div>
</template>

  
<script>
export default {
  data() {
    return {
      loggedIn: false,
      user: {
        name: 'Valters',
        surname: 'Kalcenaus',
        code: 'IT21020'
      },
      defaultColor: '#49504A',
      userColor: '#9743AD'
    };
  },
  computed: {
    fullName() {
      return `${this.user.name} ${this.user.surname}`;
    }
  },
  methods: {
    randomColor() {
      return `#${Math.floor(Math.random() * 16777215).toString(16)}`;
    },
    toggleLogin() {
      if (this.loggedIn) {
        if (confirm('Do you want to log out?')) {
          this.loggedIn = false;
          this.$emit('logout');
        }
      } else {
        if (confirm('Do you want to log in?')) {
          this.loggedIn = true;
          this.$emit('login');
        }
      }
    }
  }
};
</script>
  
 
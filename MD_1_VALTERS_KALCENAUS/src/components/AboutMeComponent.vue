<template>
    <h1>ABOUT ME</h1>
    <div class="AboutMeLine">
      <h3 class="LightText">Name: </h3>
      <h3>{{ user.name }}</h3>
    </div>
    <div class="AboutMeLine">
      <h3 class="LightText">Surname: </h3>
      <h3>{{ user.surname }}</h3>
    </div>
    <div class="AboutMeLine">
      <h3 class="LightText">Student Code: </h3>
      <h3>{{ user.code }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        user: {
          name: 'Valters',
          surname: 'Kalcenaus',
          code: 'IT21020'
        }
      };
    }
  };
  </script>
  
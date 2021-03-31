<template>
  <base-container title="Vuex" v-if="isAuth">
    <the-counter></the-counter>
    <favorite-value></favorite-value>
    <button @click="addOne">Add 10</button>
    <change-counter></change-counter>
  </base-container>
  
  <base-container title='Auth'>
    <user-auth></user-auth> 
  </base-container>
</template>

<script>
import BaseContainer from './components/BaseContainer.vue';
import theCounter from './components/theCounter.vue';
import changeCounter from './components/changeCounter.vue';
import favoriteValue from './components/favoriteValue.vue';
import userAuth from './components/UserAuth.vue';
export default {
  components: {
    BaseContainer,
    theCounter,
    changeCounter,
    favoriteValue,
    userAuth
  },
  computed:{
    isAuth(){
      return this.$store.getters.userIsAuthenticated
    }
  },
  methods:{
    addOne(){
      this.$store.dispatch('numbers/increase', {value:10})
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}


</style>
<template>

  <div id="app" class="h-100">
  <div class="container-fluid h-100">
    <div class="row h-100">
      <!--<div class="col-nd-3 vue-bg h-100 d-flex justify-content-center align-items-center" >
        <img alt="Vue logo" src="./assets/logo.png" width="100">
      </div>-->
      <div class="col-nd-9 h-100 d-flex justify-content-center align-items-center">
        <div class="col-nd-8 rounded px-5 py-4 shadow bg-white text-left">
          <Signupform />
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Signupform from './components/Signupform.vue'

export default {
  name: 'App',
  components: {
    Signupform
  }
  
}
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000305;
}
.vue-bg {
  background:lightgreen;

}
</style>

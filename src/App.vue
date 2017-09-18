<template>
  <div id="app">

    <nav class="navbar is-transparent">

      <div class="navbar-brand">

        <router-link class="navbar-item" to="/">
          <img src="http://bulma.io/images/bulma-logo.png" width="112" height="28">
        </router-link>

        <div class="navbar-burger burger" data-target="navMenu">
          <span></span>
          <span></span>
          <span></span>
        </div>

      </div>

      <div id="navMenu" class="navbar-menu">
        <div class="navbar-start">

          <!-- <a class="navbar-item" href="http://bulma.io/blog/">
            Blog
          </a>

          <a class="navbar-item" href="http://bulma.io/expo/">
            <span class="emoji">🎨</span>
            Expo
          </a>

          <a class="navbar-item" href="http://bulma.io/love/">
            <span class="emoji">❤️</span>
            Love
          </a> -->

          <a class="navbar-item" href="">
            New Project
          </a>

        </div>

        <div class="navbar-end">
        </div>

      </div>

    </nav>

    <section class="section">
    
      <!-- <div class="container"> -->
        <router-view></router-view>
      <!-- </div> -->

    </section>

  </div>
</template>

<script>
  export default {
    name: 'app'
  }
</script>

<style>

  /*@import url('https://fonts.googleapis.com/icon?family=Material+Icons');*/
  @import url('https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css');

/*  body {
    margin: 0;
  }

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }

  main {
    text-align: center;
    margin-top: 40px;
  }

  header {
    margin: 0;
    height: 56px;
    padding: 0 16px 0 24px;
    background-color: #35495E;
    color: #ffffff;
  }

  header span {
    display: block;
    position: relative;
    font-size: 20px;
    line-height: 1;
    letter-spacing: .02em;
    font-weight: 400;
    box-sizing: border-box;
    padding-top: 16px;
  }*/
</style>

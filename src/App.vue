<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-dark " id="mainNav">
      <div class="container">
        <router-link class="navbar-brand js-scroll-trigger" to="/">Diary</router-link>
        <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse" data-target="#navbarResponsive" aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation">
          Menu
          <i class="fa fa-bars"></i>
        </button>
        <div class="collapse navbar-collapse" id="navbarResponsive">
          <ul class="navbar-nav text-uppercase ml-auto">
            <li class="nav-item">
              <router-link class="nav-link js-scroll-trigger" to="/">New Entry</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link js-scroll-trigger" to="/allentry">All Entry</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <transition name="fade">
      <router-view></router-view>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      AllEntry:[],
    }
  },
  created(){
    //// Allentry(which is storing the entries)
    //this.$localStorage is a variable holding this value 'Diary'
   this.AllEntry = JSON.parse(localStorage.getItem(this.$localStorage) || '[]');
  },
}
</script>

<style>
  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s
  }
  .fade-enter, .fade-leave-active {
    opacity: 0
  }
</style>

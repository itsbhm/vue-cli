<template>
  <div id="app">

  <nav class="navbar navbar-dark bg-dark navbar-expand-lg">
    <div class="container-fluid">
      <!-- <a class="navbar-brand" href="#">VueJS App</a> -->
      <router-link class="navbar-brand" :to="'/'">VueJS App</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <!-- <a class="nav-link active" aria-current="page" href="/">Home</a> -->
            <router-link class="nav-link" :to="'/'">Home</router-link>
          </li>
          <li class="nav-item">
            <!-- <a class="nav-link" href="/contact">Contact</a> -->
            <router-link class="nav-link" :to="'/contact'">Contact</router-link>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">ITSBHM Group</a>
          </li>
        </ul>
        <form class="d-flex">
          <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
          <button class="btn btn-outline-success" type="submit">Search</button>
        </form>
      </div>
    </div>
  </nav>

    <HelloWorld/>
    
    <!-- <PostsExample></PostsExample> -->
    
    <!-- <posts-example></posts-example> -->
    
    <!-- <PostsExample/> -->

    <router-view></router-view>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import PostsExample from './components/Posts'
import Contact from './components/Contact'

export default {
  name: 'App',
  components: {
    HelloWorld,
    PostsExample,
    Contact
  }
}
</script>

<style>

@import "../node_modules/bootstrap/dist/css/bootstrap.min.css";
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>

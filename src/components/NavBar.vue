<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>
<template>
 <nav class="navbar navbar-dark bg-dark fixed-top">
  <div class="container-fluid">
            <RouterLink class="navbar-brand" to="/">Drink App</RouterLink>
    <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasDarkNavbar" aria-controls="offcanvasDarkNavbar">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="offcanvas offcanvas-end text-bg-dark" tabindex="-1" id="offcanvasDarkNavbar" aria-labelledby="offcanvasDarkNavbarLabel">
      <div class="offcanvas-header">
        <h5 class="offcanvas-title text-white" >Menu</h5>
        <button type="button" class="btn-close btn-close-white" data-bs-dismiss="offcanvas" aria-label="Close"></button>
      </div>
      <div class="offcanvas-body">
        <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
          <li class="nav-item">
             <RouterLink
                                class="nav-link active"
                                aria-current="page"
                                to="/"
                                >Home</RouterLink
                            >
          </li>
          <li class="nav-item">
            <RouterLink class="nav-link" to="/coctails"
                                >Coctails</RouterLink
                            >
          </li>
        </ul>
      </div>
    </div>
  </div>
</nav>
    <RouterView />
</template>
<style scoped>
    .offcanvas-title {
        color: #000;
    }
   
</style>

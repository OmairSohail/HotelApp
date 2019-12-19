<template>
    <div>
         <nav class="navbar">
      <div class="container">
        <div class="navbar-brand">
          <nuxt-link class="navbar-item" to="/">
            <img src="@/images/logo.png" alt="Logo">
          </nuxt-link>
          <span class="navbar-burger burger" data-target="navbarMenuHeroB">
            <span></span>
            <span></span>
            <span></span>
          </span>
        </div>
        <div id="navbarMenuHeroB" class="navbar-menu">
          <div class="navbar-end">
            <nuxt-link class="navbar-item is-active" to="/login">
              Login
            </nuxt-link>
            <nuxt-link class="navbar-item" to="/">
              Examples
            </nuxt-link>
            <nuxt-link class="navbar-item" to="/">
              Documentation
            </nuxt-link>
            <span class="navbar-item">
              <nuxt-link class="button is-success" to="/">
                <span class="icon">
                  <i class="fab fa-github"></i>
                </span>
                <span>Download</span>
              </nuxt-link>
            </span>
          </div>
        </div>
      </div>
    </nav>
    <hr>
    <nuxt/>
    </div>
</template>

<script>
export default {
    name:'OnlyNavbar'
}
</script>

<style scoped>
.navbar{
    padding-top:1rem;
}
</style>
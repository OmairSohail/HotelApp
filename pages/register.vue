<template>
    <div>
        <!--NavBar-->
    <nav class="navbar">
      <div class="container">
        <div class="navbar-brand">
          <a class="navbar-item">
            <img src="@/images/logo.png" alt="Logo">
          </a>
          <span class="navbar-burger burger" data-target="navbarMenuHeroB">
            <span></span>
            <span></span>
            <span></span>
          </span>
        </div>
        <div id="navbarMenuHeroB" class="navbar-menu">
          <div class="navbar-end">
            <a class="navbar-item is-active">
              Login
            </a>
            <a class="navbar-item">
              Examples
            </a>
            <a class="navbar-item">
              Documentation
            </a>
            <span class="navbar-item">
              <a class="button is-success ">
                <span class="icon">
                  <i class="fab fa-github"></i>
                </span>
                <span>Download</span>
              </a>
            </span>
          </div>
        </div>
      </div>
    </nav>
   <hr>
  
    <!--Register Form-->
    <div class="wrapper">
       <section>
        <b-field label="Username">
            <b-input maxlength="30" name="usernamefield"></b-input>
        </b-field>

        <b-field label="Email">
            <b-input type="email" maxlength="30" name="emailfield"></b-input>
        </b-field>

        <b-field label="Password">
            <b-input type="password" password-reveal name="passwordfield"></b-input>
        </b-field>

        <b-field label="Confirm Password">
            <b-input type="password" password-reveal name="confirmpasswordfield"></b-input>
        </b-field>
        <br>
        <b-field>   
            <button class="button is-info is-medium is-fullwidth registerbtn" type="submit">Register</button>
        </b-field>
       </section>
    </div>
    </div>
</template>

<script>

export default {
    
}
</script>

<style scoped>
.navbar{
    padding-top:1rem;
}
.wrapper{
    width:400px;
    height:700px;
    position:absolute;
    top:50%;
    left:50%;
    transform: translate(-50%,-50%);
}
</style>
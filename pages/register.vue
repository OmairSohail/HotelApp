<template>
<div>
        <!--NavBar-->
    <nav class="navbar">
      <div class="container">
        <div class="navbar-brand">
          <a class="navbar-item">
            <img src="../images/logo.png" alt="Logo">
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
            <b-input maxlength="30" v-model="name"></b-input>
        </b-field>

        <b-field label="Email">
            <b-input type="email" maxlength="30" v-model="email"></b-input>
        </b-field>

        <b-field label="Password">
            <b-input type="password" password-reveal name="passwordfield" v-model="password"></b-input>
        </b-field>

        <b-field label="Confirm Password">
            <b-input type="password" password-reveal name="confirmpasswordfield"></b-input>
        </b-field>
        <br>
        <b-field>   
            <button class="button is-info is-medium is-fullwidth registerbtn" @click="submitName()">Register</button>
        </b-field>
        <b-field>   
            <nuxt-link to="/Users">See Created Records .....</nuxt-link>
        </b-field>
       </section>
    </div>  
</div>
</template>

<script>
import {db} from '../plugins/firebase'
import uuid from 'uuid'
export default {
     
    data(){
      return{
      name: '4slash',
      email:'4slash@gmail.com',
      password:'1234'
      }
    },
    methods:{
      submitName(){
       //namesRef.push({name:this.name,email:this.email,password:this.password})
      const colref = db.collection('Users').doc(this.name)
      
      let setUser = colref.set({
        User_ID: uuid(),
        Username: this.name,
        Email: this.email,
        Create_At: Date(),
        Password:this.password
      }).then(alert('user created ...'))
    }
}
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
<template>
  <div class="two-columns">
    <div class="login-img-div">
      <img src="/roast-login.webp" class="login-image" alt="login image" />
    </div>
    <div>
      <div class="center-login-form" >
        <img class="mobile-image" src="/roast-mobile-login.webp" alt="mobile image top" />
        <img  src="/main-logo.webp" alt="logo" />
        <form>
          <div class="input-div">
            <label>Enter your email address </label>
            <input type="text" placeholder="Email address" required />
          </div>
          <div class="input-div">
            <label>Enter your password </label>
            <input type="password" placeholder="Password" required />
          </div>
          <div>
            <Link href="/"><button type="button" class="action-button">Login</button></Link>
          </div>
        </form>
        <div>
          <p>Don't have an account? <a href="#" class="links">Register</a> </p>
          <p class="center-text"><a href="#" class="links">Forgot Password</a> </p>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import Link from '../../renderer/Link.vue'
</script>

<style lang="sass" scoped>
.two-columns
  display: grid
  grid-template-columns: repeat(2, minmax(0, 1fr))

@media (max-width: 640px)
  .two-columns
    grid-template-columns: repeat(1, minmax(0, 1fr))
  
  .login-img-div
    display: none

  .center-login-form
    padding-top: 120px

.mobile-image
  position: absolute
  top: 0
  object-fit: cover
  width: 100%
  z-index: -1

@media (min-width: 640px)
  .mobile-image
    display: none
 
.center-text
  text-align: center
.login-img-div
  height: 100vh
  overflow: hidden
.login-image
  height: 100%
  width: 100%
  object-fit: cover

.center-login-form
  display: flex
  flex-direction: column
  gap: 80px
  justify-content: center
  align-items: center
  height: 100%
form
  display: flex
  flex-direction: column
  gap: 30px
.input-div
  display: flex
  flex-direction: column
  gap: 10px
input
  background-color: #EEEEEE
  border-radius: 4px
</style>
  



  
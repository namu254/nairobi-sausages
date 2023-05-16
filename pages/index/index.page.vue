<template>
  <div class="dashboard-content">
    <div class="nav">
      <img src="/menu.webp" alt="menu" class="icon" />
      <h1>Nairobi Sausages</h1>
      <img src="/user.webp" class="icon" alt="user" />
    </div>
    <div class="nav-desktop">
      <p class="hide">.</p>
      <img src="/main-logo.webp" alt="logo" />
      <img src="/user.webp" class="icon" alt="user" />
    </div>
    <p>Dashboard</p>
    <Stats />
    <p>Latest Posts</p>
    <Posts />
  </div>
</template>
<script setup>

import Stats from './stats.vue'
import Posts from './posts.vue';
</script>

<style scoped lang="sass">

$dashboard-color: #EDEAE7
$green-accent: #517148
$yellow-accent: #F3D052

.nav-desktop
  display: flex
  justify-content: space-between
  align-items: center
  padding-top: 10px
  padding-bottom: 80px
.hide
  visibility: hidden
p
  padding: 10px 0px 10px 0px
  font-family: 'Inter'
  font-style: normal
  font-weight: 600
  font-size: 14px
  line-height: 24px
  color: #595959

.nav
  display: flex
  justify-content: space-between
  align-items: center
.icon
  width: 25px
  height: 25px
  object-fit: contain
  cursor: pointer

.dashboard-content
  background-color: $dashboard-color
  padding: 0px 30px 20px 30px
.dashboard-content:hover
  box-shadow: 0 1px 2px 0 rgb(0 0 0 / 0.05)
h1 
  font-family: 'Inter'
  font-style: normal
  font-weight: 700
  font-size: 19.2233px
  line-height: 24px
  text-align: center
  color: #1C1B1F

@media (min-width: 640px)
  .nav
    display: none
@media (max-width: 640px)
 
  .dashboard-content
    padding: 0px 20px 0px 20px
  .nav-desktop
    display: none
</style>

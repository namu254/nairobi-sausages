<template>
  <div class="two-columns">
    <div class="sell-img-div">
      <img src="/farm.webp" class="login-image" alt="Sell image" />
    </div>
    <div class="scroll">
      <div class="nav">
        <Link href="/"><img src="/back.webp" alt="menu" class="icon" /></Link>

        <h1>Nairobi Sausages</h1>
        <img src="/user.webp" class="icon" alt="user" />
      </div>
      <div class="nav-desktop">
        <Link href="/"><img src="/back.webp" alt="menu" class="icon" /></Link>
        <img src="/main-logo.webp" alt="logo" />
        <p class="hide">.</p>
      </div>
      <div class="center-sell-form">
        <form>
          <div class="input-div">
            <div class="space-between">
              <label>Submit a batch</label>
              <p class="current-pig-count">{{ rangeValue }}</p>
            </div>
            <input type="range" v-model="rangeValue" min="1" max="36" step="1" required />
            <div class="space-between bold">
              <small>1</small>
              <small>36</small>
            </div>
          </div>
          <div class="input-div">
            <label>Breed</label>
            <select>
              <option value="option1">Large White</option>
              <option value="option2">Suckling white</option>
              <option value="option3">Canary Black</option>
            </select>
          </div>
          <div class="input-div">
            <label>Age</label>
            <select v-model="selectedAge">
              <option value="option1">0-3 months</option>
              <option value="option2">3-6 months</option>
              <option value="option3">6-9 months</option>
              <option value="option4">9-12 months</option>
            </select>
          </div>
          <div class="input-div">
            <label>Average Weight</label>
            <select v-model="selectedWeight">
              <option value="option1">0-30 kgs</option>
              <option value="option2">30-80 kgs</option>
              <option value="option3">80-100 kgs</option>
              <option value="option4">100-190 kgs</option>
            </select>
          </div>
          <div v-if="costOutput" class="input-div cost-per-pig">
            <label>Ask price per pig</label>
            <transition name="fade">
              <p>Ksh {{ costOutput.toLocaleString() }}</p>
            </transition>
          </div>
          <div v-if="TotalCostOutput" class="input-div cost-per-pig">
            <label>Total Price</label>
            <transition name="fade">
              <p>Ksh {{ TotalCostOutput.toLocaleString() }}</p>
            </transition>
          </div>

          <div>
            <button type="submit" class="action-button">Submit Request</button>
          </div>
        </form>

      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from 'vue';
import Link from '../../renderer/Link.vue'

const selectedAge = ref('');
const selectedWeight = ref('');
const costOutput = ref('');
const rangeValue = ref('1');
const TotalCostOutput = ref('');
let age_cost_increment = 0;
let weight_cost_increment = 0;

watch([rangeValue, selectedAge, selectedWeight], ([newPigCount, newAge, newWeight]) => {

  // Determine the added cost based on age
  switch (newAge) {
    case 'option1':
      age_cost_increment = 1000;
      break;
    case 'option2':
      age_cost_increment = 2000;
      break;
    case 'option3':
      age_cost_increment = 3000;
      break;
    case 'option4':
      age_cost_increment = 4000;
      break;
  }

  // Determine the added cost based on weight
  switch (newWeight) {
    case 'option1':
      weight_cost_increment = 5000;
      break;
    case 'option2':
      weight_cost_increment = 1000;
      break;
    case 'option3':
      weight_cost_increment = 15000;
      break;
    case 'option4':
      weight_cost_increment = 20000;
      break;
  }

  costOutput.value = age_cost_increment + weight_cost_increment
  TotalCostOutput.value = (age_cost_increment + weight_cost_increment) * newPigCount

});

</script> 
<style lang="sass" scoped>

$green-accent: #517148
$range-track-bg:  #D9D9D9
$slider-thumb-size: 26px
$input-bg: #EEEEEE

.space-between
  display: flex
  justify-content: space-between
  align-items: center
.bold
  font-family: 'Inter'
  font-style: normal
  font-weight: 600
  font-size: 14px
  line-height: 24px
.current-pig-count
  color: $green-accent
  font-family: 'Inter'
  font-style: normal
  font-weight: 700
  font-size: 18px
  line-height: 23px
  letter-spacing: 0.470588px
.nav-desktop
  display: flex
  justify-content: space-between
  align-items: center
  padding-top: 10px
  padding-bottom: 80px

h1
  font-size: 16px
.icon
  width: 35px
  height: 35px
  object-fit: contain
  cursor: pointer
.nav
  display: flex
  justify-content: space-between
  align-items: center
  padding: 5px

@media (min-width: 768px)
  .nav
    display: none
  .mobile-image
    display: none
  
input[type="range"]
  -webkit-appearance: none
  padding: 0px
  height: 8px
  border-radius: 8px
  margin-top: 20px
  background-color: $range-track-bg
  outline: none

  &::-webkit-slider-runnable-track
    height: 8px
    background-color: $range-track-bg
    border-radius: 8px

  &::-webkit-slider-thumb
    -webkit-appearance: none
    width: $slider-thumb-size
    height: $slider-thumb-size
    background-color: $green-accent
    border-radius: 50%
    margin-top: -9px

.fade-enter-active,
.fade-leave-active 
  transition: opacity 0.5s, height 0.5s

.fade-enter,
.fade-leave-to 
  opacity: 0
  height: 0
  overflow: hidden

.two-columns
  overflow: hidden
  display: grid
  grid-template-columns: repeat(2, minmax(0, 1fr))

@media (max-width: 768px)
  .two-columns
    grid-template-columns: repeat(1, minmax(0, 1fr))
  
  .sell-img-div
    display: none

  .center-sell-form
    padding: 40px
  .nav-desktop
   display: none

.mobile-image
  position: absolute
  top: 0
  object-fit: cover
  width: 100%
  z-index: -1


.center-text
  text-align: center
.sell-img-div
  height: 100vh
  overflow: hidden
.login-image
  height: 100%
  width: 100%
  object-fit: cover
.scroll
  height: 100vh
  overflow-y: scroll
.center-sell-form
  display: flex
  flex-direction: column
  gap: 80px
  justify-content: start
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
  background-color: $input-bg
  border-radius: 4px

</style>
  



  
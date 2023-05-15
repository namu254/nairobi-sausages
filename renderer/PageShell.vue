<template>
  <div>
    <slot />
  </div>
</template>

<script setup>

</script>


<style lang="sass" >
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@600&display=swap')
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap')

// Colors
$link-color: #517148
$text-color: #595959
$placeholer-color: #9D9D9D
$label-color: #1C1B1F
$button-background: #212427


p
  font-family: 'Inter'
  font-style: normal
  font-weight: 500
  font-size: 14px
  line-height: 23px
  color: $text-color
.links
  color: $link-color
  font-family: 'Inter'
  font-style: normal
  font-weight: 500
  font-size: 14px
  line-height: 23px

label
  font-family: 'Roboto'
  font-style: normal
  font-weight: 400
  font-size: 14px
  line-height: 15px
  letter-spacing: 0.376471px
  color: $label-color

.action-button
  background: $button-background
  border-radius: 40px
  padding: 15px 130px
  border: none
  color: #fff
  font-family: 'Inter'
  font-style: normal
  cursor: pointer
  font-weight: 700
  font-size: 16px
  line-height: 23px
  letter-spacing: 0.470588px


input,select
  font-family: 'Inter'
  font-style: normal
  font-weight: 400
  border: none
  padding: 15px
  font-size: 16px
  line-height: 23px
  letter-spacing: 0.470588px
  color: $placeholer-color
  background-color: #EEEEEE
  border-radius: 4px
  
option
  color: $placeholer-color
  background-color: #EEEEEE

option:selected 
  color: $placeholer-color
  background-color: #EEEEEE
body
  margin: 0
  padding: 0
  font-family: 'Roboto', sans-serif
  
input::placeholder 
  color: $placeholer-color

</style>



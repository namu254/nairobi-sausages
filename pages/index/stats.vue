<template>
    <div class="stats-box">
        <div class="order-box">
            <p class="box-p">Farm</p>
            <div class="divide-x flex">
                <p class="order-no">2</p>
                <p class="order-text">Kiambu County</p>
            </div>
            <button class="button yellow-button">Order Feeds</button>
        </div>
        <div class="order-box">
            <p class="box-p">Pigs</p>
            <div class="divide-x flex">
                <p class="order-no">36</p>
                <p class="order-text">Large White</p>
            </div>
            <button class="button green-button">Sell a batch</button>
        </div>
    </div>
</template>

<style scoped lang="sass">
$dashboard-color: #EDEAE7
$green-accent: #517148
$yellow-accent: #F3D052

.stats-box
  display: flex
  flex-direction: row
  gap: 50px
  

.order-box
  padding: 20px
  background-color: #fff
  width: max-content
  border-radius: 5px
  display: flex
  flex-direction: column
  gap: 8px

.order-text
  font-family: 'Inter'
  font-style: normal
  font-weight: 600
  font-size: 18px
  line-height: 12px
  text-transform: uppercase
  color: #595959

.yellow-button
  border: 0px
  width: 100%
  background: $yellow-accent
  
.green-button
  border: 0px
  width: 100%
  color: #fff
  background: $green-accent

.button
  border-radius: 50px
  font-family: 'Inter'
  font-style: normal
  font-weight: 700
  font-size: 14px
  line-height: 15px
  cursor: pointer
  padding: 10px 30px
 
  
.box-p
  color: $green-accent
  font-family: 'Inter'
  font-style: normal
  font-weight: 700
  font-size: 12px
  line-height: 10px
  text-transform: uppercase
  margin: 0px

.order-no
  font-family: 'Inter'
  font-style: normal
  font-weight: 600
  font-size: 50px
  line-height: 34px
  text-align: center
  text-transform: uppercase
  margin: 0px
.flex
  display: flex
  gap-x: 10px
  align-items: center
  padding: 20px
.divide-x 
  display: flex

.divide-x > * + *::before 
  content: ''
  border-left: 1px solid #9D9D9D
  margin-left: 10px
  margin-right: 10px


@media (max-width: 640px)
  .flex
    padding: 5px
  .order-no
    font-size: 20px
  .order-box
    width: 100%
    padding: 16px
  .order-text
    font-size: 10px
  .stats-box
    gap: 8px
    justify-content: stretch
  .box-p
    font-size: 10px
  .button
    padding: 10px 10px
    

</style>
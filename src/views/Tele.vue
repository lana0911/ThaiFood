<template lang="pug">
.left
  span 聯絡我們 ． 最新消息
  img#icon(src="../assets/facebook.png")
.middle
  .logo
.right
  span 相關企業
  img#icon2(src="../assets/tepan.png")

</template>


<script>
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'Tele',
  setup() {
  }
})
</script>

<style lang="sass" scoped>

#icon, #icon2
  width: 10%
  margin: 0 1%
#icon2
  width: 15%

.left, .right
  width: 30%
  height: 100%
  display: flex 
  align-items: flex-end
  justify-content: flex-end
  color: #a9aaaa
  
  span 
    margin: 2% 5%
.left
  justify-content: flex-start
.middle
  width: 40%
  height: 100%
  .logo
    width: 100%
    height: 100%
    background-size: contain
    background-repeat: no-repeat
    background-position: center
    background-image: url('../assets/logo3.png') 




</style>
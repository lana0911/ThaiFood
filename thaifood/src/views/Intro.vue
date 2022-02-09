<template lang="pug">
.foodcook
  .sticky(ref="root")
    h2#head 「 用心做最好的料理。 」
  .block
    .img#food
      h3 ▂▂   尚安心的食材   ▂▂
  .block
    .img#cook
      h3 ▂▂   拍胸脯的廚藝   ▂▂


</template>


<script>
import {  defineComponent } from 'vue'
export default defineComponent({
  name: 'Intro',
  setup() {
  }
})
</script>

<style lang="sass" scoped>

h2
  font-family: cursive, Helvetica
  margin: 0
  padding: 0
  color: #fff
  letter-spacing: -.3px
  background-image: linear-gradient(75deg, rgba(255, 255, 255, 1) 0%, rgba(255, 255, 255, 1) 33.33%, rgba(255, 255, 255, 0) 66.67%, rgba(255, 255, 255, 0) 100% )
  background-size: 300% 100%
  background-position-x: calc(100% - var(--percentage))
  background-clip: text
  -webkit-background-clip: text
  color: transparent
  transition: .5s background-position-x ease-in-out

.foodcook
  width: 100%
  height: 100%
  display: flex 
  position: relative
  justify-content: center
  .sticky
    position: absolute
    top: 0
    // height: 100vh
    height: 50%
    display: flex
    justify-content: flex-end
    align-items: center
    flex-direction: column
  .block
    width: 50%
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center
    overflow: hidden
    .img
      width: 100%
      height: 100%
      background-size: cover
      background-position: center
      background-repeat: no-repeat
      display: flex
      align-items: center
      justify-content: center      
      transition: all 0.3s ease-in-out
    #food
      background-image: url("https://images.unsplash.com/photo-1615141982883-c7ad0e69fd62?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80")
      box-shadow: 0 0 0 2000px rgba(232, 137, 1 , .86) inset
    #food:hover
      box-shadow: 0 0 0 2000px rgba(232, 137, 1 , .5) inset
      cursor: pointer
      transform: scale(1.2)
      h3
        transform: scale(.8)

    #cook
      background-image: url("https://images.unsplash.com/photo-1600565193348-f74bd3c7ccdf?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80")
      box-shadow: 0 0 0 2000px rgba(61, 32, 16, .87)  inset
    #cook:hover
      box-shadow: 0 0 0 2000px rgba(61, 32, 16, .5) inset
      cursor: pointer
      transform: scale(1.2)
      h3
        transform: scale(.8)



</style>
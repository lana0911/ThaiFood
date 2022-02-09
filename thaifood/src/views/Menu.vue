<template lang="pug">
.menu#menu
  span hi
  #paper
  #ui(ref="row")
    img(src="@/assets/header.png"  class="top-ui")
    ul(ref="row") 
      li(ref="row")
        img(src="@/assets/menu1.png")
      li(ref="row")
        img(src="@/assets/menu2.png")
      li(ref="row")
        img(src="@/assets/menu3.png")
      li(ref="row")
        img(src="@/assets/menu4.png")
      li(ref="row")
        img(src="@/assets/menu5.png")

</template>


<script>
import { ref, onMounted, defineComponent } from 'vue'
export default defineComponent({
  name: 'Menu',
  setup() {
    const row = ref(null)
    onMounted(() => {
      const rows = document.querySelectorAll('#ui ul li')
      // const ht = document.querySelector('.menu')
      const html = document.documentElement
          console.log("html=",html)
      //
      
      document.addEventListener('scroll', ()=>{
        let scrolled = html.scrollTop / 
          (html.scrollHeight - html.clientHeight)
        let total =  1 / rows.length

        for (let [index, row] of rows.entries()) {
          let start = total * index
          let end = total * (index + 1)
          console.log("scrolled=",scrolled)
          
          let progress = (scrolled - start) / (end - start)
          console.log("progress=",progress)

          if (progress >= 1) progress = 1
          if (progress <= 0) progress = 0
          
          row.style.setProperty('--progress', progress)
        }
      },false)      
    })


    return {
      row,
    }    
  }
})
</script>

<style lang="sass" scoped>

.menu
  // position: relative
  position: absolute
  bottom: 0
  width: var(--device-width)
  height: var(--device-height)      
  #paper
    width: 100%
    height: 100%
    // background-image: url("./img/menupaper.png")
    background-image: url('https://i.imgur.com/Y8UUcuQ.jpg')
    background-size: var(--device-width) var(--device-height)
  #ui
    position: absolute
    top: 0
    left: 50%
    transform: translateX(-50%)
  #ui .top-ui 
    display: block
    width: var(--ui-width)
    height: auto
    margin-top: 50px
    padding-bottom: 30px
    border-bottom: 1px solid #222
  #ui ul 
    list-style: none
    margin: 0
    padding: 0
    --progress: 0
  #ui ul li img 
    display: block
    width: var(--ui-width)
    height: auto
    margin: 10px auto
    padding-bottom: 10px
    border-bottom: 1px solid #222
    transform: scale(calc(1.8 - (0.8 * var(--progress)))) translateY(calc(-60px * (1 - var(--progress))))
    opacity: calc(var(--progress) + 1)
        
  

</style>
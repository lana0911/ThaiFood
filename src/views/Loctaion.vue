<template lang="pug">
.location#scrollBg
  .left
    h1 分店資訊
    h3 Thai Fashoion Thai Food Restarunt
    h2 體驗台泰料理的好所在
  .right
    .city
      .word

        img#icon(src="../assets/pattern_icon.png")
        h3 中部
      h2 
    .twostore
      .store#ss1(ref="s1")
        .name 台中黎明店
        .infos
          .info
            #key 電話
            #val 04-23124534
          .info
            #key 地址
            #val 
              a(href="https://www.google.com/maps/place/%E6%B3%B0%E6%BD%AE%E6%B3%B0%E5%BC%8F%E6%96%99%E7%90%86+Thai+Fashion+Thai+Restaurant/@24.137506,120.6327006,16z/data=!4m9!1m2!2m1!1z5rOw5r2u!3m5!1s0x34693d715cf0f36f:0x7128fd92451e8d9d!8m2!3d24.1374969!4d120.6371205!15sCgbms7Dmva4iA4gBAVoJIgfms7Ag5r2ukgEKcmVzdGF1cmFudA")
                span 台中市南屯區黎明路一段1003號 
                img#icon(src="../assets/place.png")
          .info
            #key 營業資訊
            #val 11:00–14:30, 17:00–21:30
        .img#s1
      .store#ss2(ref="s2")
        .name 台中大墩店
        .infos
          .info
            #key 電話
            #val 04-23145784
          .info
            #key 地址
            #val 
              a(href="https://www.google.com/maps/place/%E6%B3%B0%E6%BD%AE%E6%B3%B0%E5%BC%8F%E6%96%99%E7%90%86+Thai+Fashion+Thai+Restaurant/@24.137506,120.6327006,16z/data=!4m9!1m2!2m1!1z5rOw5r2u!3m5!1s0x34693d715cf0f36f:0x7128fd92451e8d9d!8m2!3d24.1374969!4d120.6371205!15sCgbms7Dmva4iA4gBAVoJIgfms7Ag5r2ukgEKcmVzdGF1cmFudA")
                span 台中市南屯區大墩十一街526-1-1號
                img#icon(src="../assets/place.png")
          .info
            #key 營業資訊
            #val 11:00–14:30, 17:00–21:30
        .img#s2
    button(@click="prev()") -
    button(@click="next()") >

</template>


<script>
import { defineComponent, ref } from 'vue'
export default defineComponent({
  name: 'Loctaion',
  setup() {
    const s1 = ref(null)
    const s2 = ref(null)

    const next = () =>{
      s1.value.style.left = -100 +'%'
      s2.value.style.left = 0 +'%'
    }
    const prev = () =>{
      s1.value.style.left = 0 +'%'
      s2.value.style.left = 100 +'%'
    }

    return {
      s1, s2, next, prev
    }
  }
})
</script>

<style lang="sass" scoped>

#icon
  width: 5%
  margin: 0 1%
.location
  display: flex
  background:  lightblue
  width: 100%
  height: 75%
  background-repeat: no-repeat
  background-size: 120%
  background-position: center
  // background-image: url('https://images.unsplash.com/photo-1464901978424-7ccc357ddf95?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80')
  background-image: url(../assets/bg3.png)
  box-shadow: inset 0 0 0 5000px rgba(0, 0, 0, 0.1)
  .left, .right
    height: 100%
  .left
    width: 25%
    display: flex
    flex-direction: column
    align-items: center
    writing-mode: vertical-lr
    justify-content: center
    h1
      color: #26221f
      font-size: 3rem
      margin-bottom: 10%
      margin-right: 2%
      letter-spacing: .2rem
      font-weight: bold
    h2
      font-size: 1.2rem
      font-weight: 500
    h3
      font-size: 1rem
      font-weight: 100
      color: #814925

    
  .right
    width: 75%
    .city
      width: 100%
      height: 20%
      display: flex
      align-items: flex-end
      .word
        display: flex
        color: #26221f
      h2
        height: 1.5rem
      .word:hover
        cursor: pointer
        h2
          border-top: 2px solid #000
          animation: border_anim .3s linear forwards
    @keyframes border_anim 
      0%
        width: 0%
      100%
        width: 100%
      
    .twostore
      width: 100%
      height: 80%
      display: flex   
      justify-content: space-between
      align-items: center
      .store
        width: 48%
        height: 90%
        .name
          height: 15%
          font-size: 1.2rem
          font-weight: bolder
          border-bottom: .04rem solid linear-gradient(-90deg, #FFBA33, #B3450A)
          display: flex
          align-items: center
          font-weight: bold
        .infos
          // height: 35%
          width: 100%
          .info
            display: flex
            width: 100%
            #key
              font-weight: bold
              width: 20%
              border-right: 2px solid #9c9c9c
              margin-right: 5%
              margin-bottom: 2%
              color: #814925
            #val 
              width: 70%
              a
                color: #000
                text-decoration: none
              a:hover
                color: #814925


        .img
          height: 50%
          width: 80%
          background-size: cover
          box-shadow: inset 0 0 0 2000px #00000021
          border-radius: 10px
        #s1
          background-image: url(https://scontent.frmq5-1.fna.fbcdn.net/v/t1.6435-9/34663510_1826425070985469_8618526833534566400_n.jpg?_nc_cat=109&ccb=1-5&_nc_sid=0debeb&_nc_ohc=dbzGro2MRokAX9J1XqE&_nc_ht=scontent.frmq5-1.fna&oh=00_AT9htIXK9RQFdsSfRYjVjeXj15MBUxBIYkmJfk5KLwfPCQ&oe=6228592B)
        #s2
          background-image: url(https://scontent.frmq5-1.fna.fbcdn.net/v/t1.6435-9/72135108_510192266227602_1215091559943372800_n.jpg?_nc_cat=111&ccb=1-5&_nc_sid=e3f864&_nc_ohc=D4jAhhyVEgYAX-18USB&_nc_ht=scontent.frmq5-1.fna&oh=00_AT8ZcxB8QA8utIQ_WlaGMohVitgFiZJHMzwzHYeAhtFOrA&oe=6227A5B3)
      .store:nth-child(1)
        border-right: 1px solid #000      


  @media screen and (max-width: 768px) 
    flex-direction: column
    .left
      width: 100%
      writing-mode: initial
      height: 25%
      h1
        margin-bottom: .5%
    .right
      width: 100%
      .city
        align-items: flex-start
        height: auto
        justify-content: center
      .twostore
        display: flex 
        background: lightblue  
        overflow: hidden
        position: relative
        .store
          margin: 2rem
          border: 1px solid #000
          width: 85%
          height: 85%
          position: absolute
          transition: all 2s  
          transition-delay: .1s
          display: flex
          flex-direction: column
          justify-content: center
          align-items: center
          .infos
            .info
              justify-content: center
              #key
                width: 15%
              #val
                width: 50%

        #ss1
          left: 0%
        #ss2
          left: 200%    
</style>
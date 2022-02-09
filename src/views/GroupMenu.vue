<template lang="pug">
.head
  h2 超值合菜
  span 二人放鬆、三人品味、四人享受、八人暢飽
.meals
  .block
    .meal
      a#tag 雙人套餐
    aritcal.intro 
      span 4菜1湯   
      span 贈 白飯2碗 飲料/甜點2份
      .quote
        span 情侶約會的最佳選擇
  .block
    .meal
      a#badge 黎明店限定
      a#tag 三人套餐
    aritcal.intro 
      span 5菜1湯
      span 贈 白飯3碗 + 飲料/甜點3份
      .quote
        span 仨人一起吃，不多也不少
  .block
    .meal
      a#tag 四人套餐
    aritcal.intro 
      span 6菜1湯
      span 贈 白飯6碗 + 飲料/甜點6份
      .quote
        span 滿足小家庭每個人的味蕾
  .block
    .meal
      a#badge 大墩店限定
      a#tag 八人套餐
    aritcal.intro 
      span 9菜1湯
      span 贈 白飯8碗 + 飲料/甜點8份
      .quote
        span 家族聚餐不用驚！只怕你吃不完

</template>


<script>
import {  defineComponent } from 'vue'
export default defineComponent({
  name: 'GroupMenu',
  setup() {
  }
})
</script>

<style lang="sass" scoped>
.head
  height: 30%
  display: flex
  flex-direction: column
  align-items: center
  justify-content: center
  h2
    font-size: 3rem
  span 
    font-size: medium
.block
  display: flex
  height: 100%
  width: 100%
  flex-direction: column

  position: relative
  

.meals
  display: flex
  justify-content: space-evenly
  align-items: center
  width: 100%
  height: 100%

  .meal
    width: 85%
    height: 55%
    background: red
    margin: 1rem .3rem
    background-size: cover
    background-repeat: no-repeat
    background-position: center  
    position: relative
    display: flex
    justify-content: center
    transition:  .2s

    #tag
      position: absolute
      bottom: -5%
      padding: 0.5rem 25%
      background: RGB(221, 122, 59)
      font-weight: bolder
      letter-spacing: .2rem
    #badge
      position: absolute
      top: -1%
      right: 0
      padding: 0.5rem
      background: #fffafa
      font-weight: bolder
      letter-spacing: .5rem
      font-size: smaller
      box-shadow: 3px 3px 2px 0 #9e9e9e, -2px -1px 2px 0 #ffc10700
      color: #000
      writing-mode: vertical-lr      

  .meal:hover
    position: relative
    top: -.5rem 
    box-shadow: 5px 5px 5px 4px #1b1917
    
  .intro
    margin: 15% auto
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center
    .quote
      display: flex
      padding: 0 0.5rem
      border-left: 5px double #dda43b
      border-right: 5px double #dda43b
      justify-content: center
      color: #dda43b
      font-size: smaller
      margin-top: 1rem
  .block:nth-child(1)
    .meal
      margin-left: 1rem
      background-image: url(https://scontent.frmq5-1.fna.fbcdn.net/v/t1.6435-9/96082682_2283771975250774_6260483156877508608_n.jpg?_nc_cat=103&ccb=1-5&_nc_sid=730e14&_nc_ohc=r_YnJmtwxwoAX8Nxc4Z&_nc_ht=scontent.frmq5-1.fna&oh=00_AT-_sBY-kUFq-JnCbWjWl8jaxRk6_I16cuus055gT6CQZA&oe=6227EE90)
  .block:nth-child(2)
    .meal
      background-image: url(https://scontent.frmq5-1.fna.fbcdn.net/v/t1.6435-9/34444421_1825622147732428_5329945906282233856_n.jpg?_nc_cat=101&ccb=1-5&_nc_sid=8bfeb9&_nc_ohc=ZBISLfbpO4oAX-OaolI&_nc_ht=scontent.frmq5-1.fna&oh=00_AT_1_Dsn55Omxqi3yUg4Slxq3hzZhwoDh4b1WLn4hTETfw&oe=622754C7)
  .block:nth-child(3)
    .meal
      background-image: url(https://scontent.frmq5-1.fna.fbcdn.net/v/t1.6435-9/98001926_2292118497749455_7354389066353213440_n.jpg?_nc_cat=101&ccb=1-5&_nc_sid=730e14&_nc_ohc=cnJZDB_qnqkAX-aSF-8&_nc_ht=scontent.frmq5-1.fna&oh=00_AT_r7_4RuOebWM4OXS4mgUKCIx3fWDWK7UvWNL90aIVDog&oe=6227631D)
  .block:nth-child(4)
    .meal
      margin-right: 1rem
      background-image: url(https://scontent.frmq5-1.fna.fbcdn.net/v/t1.6435-9/131300047_2454632461498057_767929576829852291_n.jpg?_nc_cat=105&ccb=1-5&_nc_sid=8bfeb9&_nc_ohc=MnxJnWO8Pw4AX96JlzF&_nc_ht=scontent.frmq5-1.fna&oh=00_AT-a7U9eWH5yGW9EsuH-e_WQ9Ob4D8XkKaJBCWTImgeeUw&oe=6226FE31)


</style>
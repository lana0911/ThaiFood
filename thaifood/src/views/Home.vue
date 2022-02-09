<template lang="pug">
#home
  .banner#scrollBg
    .logo
  .introduction
    Intro()
  .menuArea#scrollBg
    Menu()
  .groupMenu
    GroupMenu()
  .realMenu#scrollBg
    RealMenu()
  .location#scrollBg
    Loctaion()
  .tele
    Tele()
</template>



<style lang="sass" scoped>

@import '@/assets/style.sass'


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

</style>


<script>
// @ is an alias to /src
import { ref } from 'vue'
import Menu from './Menu'
import GroupMenu from './GroupMenu'
import RealMenu from './RealMenu'
import Intro from './Intro'
import Tele from './Tele'
import Loctaion from './Loctaion'

export default {
  name: 'Home',
  components: {
    Menu, GroupMenu, RealMenu, Intro, Tele, Loctaion
  },
  setup() {
    const root = ref(null)


    document.addEventListener('scroll', ()=>{
      let h2 = root.value
      let scrolled = document.documentElement.scrollTop / 
        (document.documentElement.scrollHeight - document.documentElement.clientHeight)
      h2.style.setProperty('--percentage', `${scrolled * 100}%`)
    })

    return {
      root,
    }
  }
}
</script>
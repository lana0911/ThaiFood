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
  Loctaion()
  .tele
    Tele()
</template>



<style lang="sass" scoped>

@import '@/assets/style.sass'

.menuArea
  width: 100%
  height: 150%
  position: relative
  overflow: hidden
  display: flex
  justify-content: center
  background-image: url(../assets/bg3.png)

  box-shadow: inset 0 0 0 5000px rgba(0, 0, 0, 0.5)


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
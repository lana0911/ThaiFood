<template lang="pug">
.wrap
  .store#s1(ref="s1")
    span hi1
  .store#s2(ref="s2")
    span hi2
button(@click="prev()") -
button(@click="next()") >
button#bt Test
#foo
</template>

<script>
import {ref} from 'vue'
export default {
  setup(){
    const s1 = ref(null)
    const s2 = ref(null)




    const next = () =>{
      // ss1.style.setProperty('left', '-100%')
      s1.value.style.left = -100 +'%'
      s2.value.style.left = 0 +'%'
    }
    const prev = () =>{
      // ss1.style.setProperty('left', '-100%')
      s1.value.style.left = 0 +'%'
      s2.value.style.left = 100 +'%'
    }

    return {
      s1, s2, next, prev
    }
  }
}
</script>


<style lang="sass">
.wrap
  height: 30vh
  display: flex 
  background: lightblue  
  position: relative
  .store
    margin: 2rem
    border: 1px solid #000
    width: 100%
    height: 50%
    position: absolute
    transition: all 2s  
    transition-delay: .1s
  #s1
    left: 0%
    // transition: all 2s 
  #s2
    left: 200%    
    // transition: all 2s 



p
  padding-left: 60px
#foo
  border-radius: 50px
  width: 50px
  height: 50px
  background: #c00
  position: absolute
  top: 0
  left: 0

  transition:  all 5s  
  </style>

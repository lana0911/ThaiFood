<template lang="pug">
.title
  h2 完整菜單
.bookarea
  button(id="prev-btn" ref='prevBtn') ◀

  .book#book(ref="book")
    .paper#p1(ref="paper1")
      .front
        .front-content#f1
      .back
        .back-content#b1

    .paper#p2(ref="paper2")
      .front
        .front-content#f2
      .back
        .back-content#b2

    .paper#p3(ref="paper3")
      .front
        .front-content#f3
      .back
        .back-content#b3
          
    .paper#p4(ref="paper4")
      .front
        .front-content#f4
      .back
        .back-content#b4
  button(id="prev-btn"  ref='nextBtn') ▶

</template>


<script>
import { onMounted, ref, defineComponent } from 'vue'
export default defineComponent({
  name: 'RealMenu',
  setup() {
    const prevBtn = ref()
    const nextBtn = ref()
    const book = ref()

    const paper1 = ref()
    const paper2 = ref()
    const paper3 = ref()
    const paper4 = ref()
    onMounted(() => {
      prevBtn.value.addEventListener("click", goPrevious);
      nextBtn.value.addEventListener("click", goNext);
    })
    // References to DOM elements

    // Business Logic
    let currentState = 1;
    let numOfPapers = 4;
    let maxState = numOfPapers + 1;


    function openBook() {
        book.value.style.transform = "translateX(50%)";
        // prevBtn.value.style.transform = "translateX(-180px)";
        // nextBtn.value.style.transform = "translateX(180px)";
    }

    function closeBook(isFirstPage) {
        if(isFirstPage) {
            book.value.style.transform = "translateX(0%)";
        } else {
            book.value.style.transform = "translateX(100%)";
        }
        // prevBtn.value.style.transform = "translateX(0px)";
        // nextBtn.value.style.transform = "translateX(0px)";
    }

    function goNext() {
        if(currentState < maxState) { 
            switch(currentState) {
                case 1:
                    openBook();
                    paper1.value.classList.add("flipped");
                    paper1.value.style.zIndex = 1;
                    break;
                case 2:
                    paper2.value.classList.add("flipped");
                    paper2.value.style.zIndex = 2;
                    break;
                case 3:
                    paper3.value.classList.add("flipped");
                    paper3.value.style.zIndex = 3;
                    break;
                case 4:
                    closeBook(false);
                    paper4.value.classList.add("flipped");
                    paper4.value.style.zIndex = 4;
                    break;
                default: 
                    throw new Error("unkown state");    
            }

            currentState++;
        }
    }

    function goPrevious() {
        if(currentState > 1) {
            switch(currentState) {
                case 2:
                    closeBook(true);
                    paper1.value.classList.remove("flipped");
                    paper1.value.style.zIndex = 4;
                    break;
                case 3:
                    paper2.value.classList.remove("flipped");
                    paper2.value.style.zIndex = 3;
                    break;
                case 4: 
                    // openBook()
                    paper3.value.classList.remove("flipped");
                    paper3.value.style.zIndex = 2;
                    break;
                case 5: 
                    openBook()
                    paper4.value.classList.remove("flipped");
                    paper4.value.style.zIndex = 1;
                    break;
            }

            currentState--;
        }
    }

    return{
      prevBtn, nextBtn, book, 
      paper1, paper2, paper3, paper4

    }
  }
})
</script>

<style lang="sass" scoped>
.bookarea
    width: 100%
    height: 75%
    display: flex
    justify-content: center
    align-items: center

.title
  width: 100%
  height: 25%
  // background-color: #000
  background-image: url('../assets/whitebg.png')
  background-size: contain
  display: flex
  flex-direction: column
  align-items: center
  justify-content: center
  h2
    font-size: 3rem
  span 
    font-size: medium
/* Button */
button 
    // border: 1px solid
    border-radius: 50%
    color: #fff
    background-color: #000
    height: 2rem 
    width: 2rem
    margin: 1rem 
    padding: .2rem
    cursor: pointer
    transition: transform 0.5s
    z-index: 500
button:focus 
    outline: none
button:hover i 
    color: rgb(102, 102, 102)

/* Book */
.book 
    width: 25%
    height: 96%
    position: relative
    transition: transform 0.5s
.paper 
    height: 100%
    width: 100%
    position: absolute
    top: 0
    left: 0
    perspective: 1500px
    
.front 
    backface-visibility: hidden
.front, .back 
    position: absolute
    width: 100%
    height: 100%
    top: 0
    left: 0
    display: flex
    justify-content: center
    align-items: center
    transform-origin: left
    transition: transform 0.5s
.front 
    z-index: 1
.back 
    z-index: 0

.front-content, .back-content 
    width: 100%
    height: 100%
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center
    background-size: contain
    background-repeat: no-repeat
.back-content 
    transform: rotateY(180deg)


/* Paper Flipped */
.flipped .front, .flipped .back 
    transform: rotateY(-180deg)


/* Paper Z-index */
#p1 
    z-index: 4
#p2 
    z-index: 3
#p3 
    z-index: 2
#p4 
    z-index: 1


#f1
  background-image: url('../assets/p1.jpg')
#b1

  background-image: url('../assets/p1b.jpg')
#f2
  background-image: url('../assets/p2f.jpg')
#b2

  background-image: url('../assets/p2b.jpg')
#f3
  background-image: url('../assets/p3f.jpg')
#b3
  background-image: url('../assets/p3b.jpg')

#f4
  background-image: url('../assets/p4f.jpg')
#b4
  background-image: url('../assets/p4.jpg')


</style>
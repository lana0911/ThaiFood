<template>
  <div id="nav">
    <router-link to="/"></router-link> |
    <a>
      <img src="./assets/ele.png"/>
    </a>
  </div>
  <router-view/>
</template>

<style lang="scss">

*{
  margin: 0;
  padding: 0;
  list-style: none;
}
html, body {
    height: 100%;
    padding: 0;
    margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  height: 100%;
  display: inline;
}

#nav{
  position: fixed;
  top: 0;
  width: 100%;
  // background: #ffc671a6;
  height: 5vh;
  display: flex;
  justify-content: flex-end;
  z-index: 1000;
  a{
    img
    {
      width: 3rem;
      height: 3rem;
      margin: 1rem 1rem ;
      border: 1px solid #fff;
      border-radius: 50%;
      padding: .2rem;
      background-color: #fff;
    }
  }
}
:root {
  --percentage: 0%;
  --device-width: 515px;
  --device-height: 890px;
  --ui-width: 426px;
}


</style>

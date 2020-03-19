<template>
<div id="app">
  <div id="page">
    <div id="menu">
      <div id="brand">
        <router-link to="/">
          <img src="/images/korea_food.jpg">
        </router-link>
      </div>
      <div id="side">
        <router-link to="/browse">
          <div class="menu-item browse">
            <img src="/images/browser.jpg">
            <p>Browse</p>
          </div>
        </router-link>
        <router-link to="/cart">
          <div class="menu-item">
            <img src="/images/cart.jpg">
            <p>{{this.$root.$data.numberOfItems}} items</p>
          </div>
        </router-link>
      </div>
    </div>
    <router-view />
  </div>
  <footer id="footer"><a href="https://github.com/Shawn45/cp3.git">Github Repository</a></footer>
</div>


</template>



<style>
* {
  box-sizing: border-box;


  margin: 0;
  padding: 0;
}

html, body {
  //margin: 50px 100px;
  font-family: 'Nanum Pen Script', cursive;

  height: 100%;


}
a {
  color: gray;
}

#app {
  height: 100%;
}

#page {
    min-height: 100%;
    margin-left: 100px;
    margin-right: 100px;
}

#menu {

  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
  padding-top: 50px;
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: right;
}

#side img {
  height: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}

#footer {
    background-color: #FFD300;
    position: relative;
    height: 20px;
    margin-top: -20px;
    margin-left: 100px;
    margin-right: 100px;
    clear: both;
    //width: 100%;
    text-align: center;
    color: white;

}

</style>

<template>
<div id="app">
  <div class="pure-menu">
    <span class="pure-menu-heading"><b>Math Help</b></span> 
    <ul class="pure-menu-list">
      <li class="pure-menu-item">
        <router-link to="/" class="pure-menu-link">Home</router-link>
      </li>
      <li class="pure-menu-item">
        <router-link to="/calculator" class="pure-menu-link">Calculator</router-link>
      </li>
      <li class="pure-menu-item">
        <router-link to="/mypage" class="pure-menu-link">My Page</router-link>
      </li>
    </ul>
  </div>
  <div class="content">
    <router-view />
  </div>
</div>
</template>

<style>
/* https://color.adobe.com/Ventana-Azul-color-theme-2159606/?showPublished=true */
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  font-size: 18px;
  display: flex;
  min-height: 100%;
}
.pure-menu {

  text-align: left;
  background: #F5F3EF;
}
.pure-menu-heading {
  color: #fff;
  font-size: 1.2em;
  padding: 20px 20px;
  background-color: #489F97;
  margin-bottom: 50px;
}
.pure-menu-link {
  color: #A58153;
  padding: 3px 50px;
  font-weight: 800;
  margin-top: 20px;
}
.pure-menu-link:hover {
  background: #489F97;
}
.pure-menu-link.router-link-exact-active {
  background: #fff;
  color: #489F97;
}
.content {
  margin: 50px 100px;
}
html {
  height: 100%;
  box-sizing: border-box;
}
body {
  height: 100%;
}
*,
*:before,
*:after {
  box-sizing: inherit;
  /* https://css-tricks.com/box-sizing/ */
}
.error {
  color: #489F97;
}
.pure-button-primary {
  background-color: #489F97;
}
/* Modals */
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, .5);
  display: table;
  transition: opacity .3s ease;
}
.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}
.modal-container {
  width: 500px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
  transition: all .3s ease;
  font-family: Helvetica, Arial, sans-serif;
}
.modal-header h1 {
  margin-bottom: 30px;
  font-size: 1.5em;
}
.modal-body {
  margin: 0;
}
.modal-body input {
  margin-bottom: 20px;
  height: 30px;
}
.modal-footer {
  margin-top: 20px;
  display: flex;
  justify-content: space-between;
}
.modal-default-button {
  float: right;
}

.modal-enter {
  opacity: 0;
}
.modal-leave-active {
  opacity: 0;
}
.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
footer {
  background-color: #F5F3EF;
  color: #A58153;
  bottom: 0;
  left: 0;
  right: 0;
  height: 4%;
  position: fixed;
  text-align: center;
}
footer a {
    color: #A58153;
}
</style>
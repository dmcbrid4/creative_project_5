<template>
  <div class="home">
    <div class="header">Mathematical Calculator</div>
    <div class="explanation">
  <p>This is a mathematical calculator that can help you solve some tough math equations. Some of these equations include:</p>
  </div>
  <div class="grid">
    <div>Simplify<br>Ex: 2^2 + 2(2) = 8</div>
    <div>Factor<br>Ex: x^2 - 5x = x (x - 5)</div>
    <div>Derive<br>Ex: 4x^3 = 12x^2</div>
    <div>Integrate<br>Ex: x^2 = 1/3x^3 + C</div>
    <div>Find 0's<br>Ex: x^2 - 5x + 4 = [4, 1]</div>
    <div>Trig Functions<br>Ex: sin(pi) = 0</div>
  </div>
  <footer class="footer">
  <div class="container">
    <span class="text-muted"><a href="https://github.com/jshirl10/Creative-Project-5.git">TA Link</a></span>
  </div>
</footer>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>
.header {
  background-color: #F5F3EF;
  width: 100%;
  border: 5px solid #489F97;
  padding: 1%;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
  border-radius: 25px;
  color: #A58153;
  font-weight: bold;
  font-size: 25px;
  margin-top: 2%;
}
.explanation {
  background-color: #F5F3EF;
  width: 85%;
  border: 5px solid #489F97;
  padding: 1%;
  margin-left: auto;
  margin-right: auto;
  margin-top: 4%;
  text-align: center;
  border-radius: 25px;
  color: #A58153;
  font-weight: bold;
  font-size: 25px;
}
.grid {
  display: grid;
  grid-template-columns: auto auto auto;
}
.grid div {
  background-color: #F5F3EF;
  width: 90%;
  border: 5px solid #489F97;
  padding: 1%;
  margin-left: auto;
  margin-right: auto;
  margin-top: 10%;
  text-align: center;
  border-radius: 25px;
  color: #A58153;
  font-weight: bold;
  font-size: 20px;
}
</style>
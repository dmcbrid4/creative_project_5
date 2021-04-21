<template>
<div>
  <div v-if="user" class="header">
    <div>
      <h1>Calculator</h1>
    </div>
    <div class="button">
      <p><button @click=" logout" class="pure-button pure-button-primary">Logout</button></p>
    </div>
    <fieldset class="submitEquation">
    <div>
      <h1>Choose the type of computation you want:</h1>
      <div class="calculatorTypes">
        <button class="computeTypes" v-on:click="derivativeCalculator()">Derive</button>
        <button class="computeTypes" v-on:click="simplifyEquation()">Simplify</button>
        <button class="computeTypes" v-on:click="factorEquation()">Factor</button>
        <button class="computeTypes" v-on:click="integrationCalculator()">Integrate</button>
        <button class="computeTypes" v-on:click="findZeroes()">Zeroes</button>
        <button class="computeTypes" v-on:click="sin()">Sine</button>
        <button class="computeTypes" v-on:click="cosine()">Cosine</button>
        <button class="computeTypes" v-on:click="tangent()">Tangent</button>
      </div>
      <h1>{{computationChoice}}</h1>
        <input id="mathInput" v-model="equation" type="text"><br><br>
        <input id="mathSubmit" type="button" v-on:click="mathSubmit" value="Solve">
      </div>
    </fieldset>
      <div id="mathResults">
        <h2>{{current.result}}</h2>
      </div>
  </div>
  <div v-else>
    <p>If you would like calculate a function, please register for an account or login.</p>
    <router-link to="/register" class="pure-button">Register</router-link> or
    <router-link to="/login" class="pure-button">Login</router-link>
  </div>
  <footer class="footer">
  <div class="container">
    <span class="text-muted"><a href="https://github.com/dmcbrid4/creative_project_5">Github: Hours spent: 7</a></span>
  </div>
</footer>
</div>
</template>

<script>
export default {
  name: 'calculator',
  data() {
    return {
      equation: " ",
      current: {
        operation: 'derive',
        expression: '',
        result: '',
      },
    }
  },
  computed: {
    user() {
      return this.$store.state.user;
    },
    computationChoice() {
      return this.current.operation.toUpperCase();
    }
  },
  created() {
    this.$store.dispatch("getUser");
  },
  methods: {
    async logout() {
      try {
        this.error = await this.$store.dispatch("logout");
      } catch (error) {
        console.log(error);
      }
    },
    async mathSubmit() {
      await this.$store.dispatch("mathSubmit");
    },
    derivativeCalculator() {
      this.current.operation = "derive";
    },
    simplifyEquation() {
      this.current.operation = "simplify";
    },
    factorEquation() {
      this.current.operation = "factor";
    },
    integrationCalculator() {
      this.current.operation = "integrate";
    },
    findZeroes() {
      this.current.operation = "zeroes";
    },
    sin() {
      this.current.operation = "sin";
    },
    cosine() {
      this.current.operation = "cos";
    },
    tangent() {
      this.current.operation = "tan";
    }
  }
}
</script>

<style scoped>
.pure-button {
  margin: 0px 20px;
  background-color: #489F97;
  color: #fff;
}
.header {
  display: flex;
}
.header .button {
  margin-left: 50px;
  order: 2;
}
h1 {
  color: #A58153;
}
.submitEquation {
  background-color: #F5F3EF;
  width: 80%;
  border: 5px solid #489F97;
  padding: 1%;
  text-align: center;
  border-radius: 25px;
  color: #A58153;
  font-weight: bold;
  font-size: 20px;
  margin-top: 8%;
}
</style>
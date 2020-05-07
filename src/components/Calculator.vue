<template>
  <div class="calculator">
    <div class="display">{{current || '0'}}</div>
    <div @click="clear" class="btn">AC</div>
    <div @click="sign" class="btn">+/-</div>
    <div class="btn">%</div>
    <div class="btn operator">+</div>
    <div class="btn">7</div>
    <div class="btn">8</div>
    <div class="btn">9</div>
    <div class="btn operator">x</div>
    <div class="btn">4</div>
    <div class="btn">5</div>
    <div class="btn">6</div>
    <div class="btn operator">-</div>
    <div class="btn">1</div>
    <div class="btn">2</div>
    <div class="btn">3</div>
    <div class="btn operator">+</div>
    <div class="btn zero">0</div>
    <div class="btn">.</div>
    <div class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  data() {
    return{
      current:'999',

    }
  },
  methods: {
    clear() {
      this.current = '';
    },
    sign() {
      this.current = this.current.charAt(0) === '-' ?
        this.current.slice(1) : ''; 
    }
  }
}
</script>


<style  scoped>
.calculator {
  width: 400px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
  font-size: 40px;
  border: 1px red solid;
  margin: 0 auto;
}
.display {
  grid-column: 1/5;
  background-color: green;
  color: white;
  text-align: right;
  padding: 2%;
}
.zero {
  grid-column: 1/3;
}
.btn {
  background-color: #eee;
  border: 1px black solid;
}
.operator {
  background-color: lightsalmon;
  color: white;
}
</style>

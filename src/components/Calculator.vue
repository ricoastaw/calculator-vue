<template>
  <div class="calculator">
    <div class="display">{{current || '0'}}</div>
    <div @click="clear" class="btn">AC</div>
    <div @click="sign" class="btn">+/-</div>
<<<<<<< HEAD
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
=======
    <div @click="percent" class="btn">%</div>
    <div @click="divide" class="btn operator">/</div>
    <div @click="append('7')" class="btn">7</div>
    <div @click="append('8')" class="btn">8</div>
    <div @click="append('9')" class="btn">9</div>
    <div @click="times" class="btn operator">x</div>
    <div @click="append('4')" class="btn">4</div>
    <div @click="append('5')" class="btn">5</div>
    <div @click="append('6')" class="btn">6</div>
    <div @click="sub" class="btn operator">-</div>
    <div @click="append('1')" class="btn">1</div>
    <div @click="append('2')" class="btn">2</div>
    <div @click="append('3')" class="btn">3</div>
    <div @click="add" class="btn operator">+</div>
    <div @click="append('0')" class="btn zero">0</div>
    <div @click="dot" class="btn">.</div>
    <div @click="equal" class="btn operator">=</div>
>>>>>>> 54f5681b16eb137e6a316992c3482465f62a9b5f
  </div>
</template>

<script>
export default {
  data() {
    return{
<<<<<<< HEAD
      current:'999',

=======
      previous: null,
      current:'',
      operator: null,
      operatorClicked: false,
>>>>>>> 54f5681b16eb137e6a316992c3482465f62a9b5f
    }
  },
  methods: {
    clear() {
      this.current = '';
    },
    sign() {
<<<<<<< HEAD
      this.current = this.current.charAt(0) === '-' ?
        this.current.slice(1) : '-s{this.current}'; 
=======
      this.current = this.current.charAt(0) === '-'  ?
        this.current.slice(1) : `-${this.current}` ; 
    },
    percent(){
      this.current = `${parseFloat(this.current)/100}`
    },
    append(number){
      if(this.operatorClicked){
        this.current = '';
        this.operatorClicked= false;
      }

      this.current =`${this.current}${number}`;
    },
    dot(){
      if (this.current.indexOf('.')=== -1){
        this.append('.');
      }
    },
    setPrevious(){
      this.operatorClicked = true;
      this.previous = this.current;
    },
    divide(){
      this.operator = (a,b) => a/b;
      this.setPrevious();
    },
    times(){
      this.operator = (a,b) => a*b;
      this.setPrevious();
    },
    sub(){
 
      this.operator = (a,b) => a-b;
      this.setPrevious();
    },
    add(){
      this.operator = (a,b) => a+b;
      this.setPrevious();
    },
    equal(){
      this.current = `${this.operator(
        parseFloat(this.current),
        parseFloat(this.previous)
      )}`;
      this.previous=null;
>>>>>>> 54f5681b16eb137e6a316992c3482465f62a9b5f
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

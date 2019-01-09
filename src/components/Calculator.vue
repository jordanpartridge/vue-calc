<template>
  <div class="calc--wrapper">
   <div class="display">DISPLAY HERE</div>
   <div class="button">C</div>
   <div class="button">+/-</div>
   <div class="button ">%</div>
   <div class="button operator">÷</div>
   <div class="button">7</div>
   <div class="button">8</div>
   <div class="button">9</div>
   <div class="button operator">X</div>
   <div class="button">4</div>
   <div class="button">5</div>
   <div class="button">6</div>
   <div class="button operator">-</div>
   <div class="button">1</div>
   <div class="button">2</div>
   <div class="button">3</div>
   <div class="button operator">+</div>
   <div class="button double">0</div>
   <div class="button">.</div>
   <div class="button operator">=</div>

  </div>
</template>

<script>
export default {
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.calc--wrapper {
  /**
   * Grid Styles
   * Child elements will be 4 columns
   */
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);

  /**
   * Fixed width centered enlarge text
   */
    margin: auto;
    width: 600px;
    font-size: 45px;

}
.display{
  grid-column: 1 / 5;
  background-color: #1e1e1e;
  color: #ffffff;
}
.double {
  grid-column: 1/3;
}
.button{
  background-color:  #eee;
  border: 1px solid;
  height: 75px;
  padding: 15px;

 

}
.operator{
  background-color: teal;
  color: white;
  border-color: black;
}
</style>

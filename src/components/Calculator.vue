<template>
  <div class="calc--wrapper">
   <div class="display">{{display_value || '0'}}</div>
   <div @click="clear" class="button">C</div>
   <div @click="sign" class="button">+/-</div>
   <div @click="percent" class="button ">%</div>
   <div class="button operator">÷</div>
   <div v-on:click = "onClick" class="button">7</div>
   <div v-on:click = "onClick" class="button">8</div>
   <div v-on:click = "onClick"  class="button">9</div>
   <div class="button operator">X</div>
   <div v-on:click = "onClick" class="button">4</div>
   <div v-on:click = "onClick" class="button">5</div>
   <div v-on:click = "onClick" class="button">6</div>
   <div class="button operator">-</div>
   <div v-on:click = "onClick" class="button">1</div>
   <div v-on:click = "onClick" class="button">2</div>
   <div v-on:click = "onClick" class="button">3</div>
   <div class="button operator">+</div>
   <div v-on:click = "onClick" class="button double">0</div>
   <div class="button">.</div>
   <div class="button operator">=</div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      display_value: '2',
      saved_value: '',
      operator: ''
    }
  },
  methods: {
    clear () {
      this.display_value = ''
    },
    sign () {
      /*
       * reverse the sign of i:
       * i - (i * 2)
       */
      this.display_value = `${parseFloat(this.display_value)}`
      this.display_value -= (this.display_value * 2)
    },
    percent () {
      this.display_value = `${parseFloat(this.display_value)}`
      this.display_value /= 100
    },
    onClick: function (e) {
      let number = e.srcElement.innerHTML
      this.display_value = this.display_value.concat(number)
    }
  }
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
  color:  #eee;
  background: #11ee11;
  border: 1px solid;
  height: 75px;
  padding: 15px;
  border-color: #cccccc;

}
.operator{
  background-color: #eeeeee;
  color: #11ee11;
}
</style>

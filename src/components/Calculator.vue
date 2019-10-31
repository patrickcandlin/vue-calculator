<template>
  <div id="calculator">
    <div id="screen-container">
      <div id="screen">{{ screenValue }}</div>
    </div>

    <div id="buttons-container">
      <div class="buttons">
        <span @click="clearPressed"  class="operator" id="clear">C</span>
        <span @click="dividePressed" class="operator">÷</span>
        <span @click="operatorPressed" class="operator">*</span>
        <span @click='numberPressed'>7</span>
        <span @click='numberPressed'>8</span>
        <span @click='numberPressed'>9</span>
        <span @click="operatorPressed" class="operator">-</span>
        <span @click='numberPressed'>4</span>
        <span @click='numberPressed'>5</span>
        <span @click='numberPressed'>6</span>
        <span @click="operatorPressed" class="operator">+</span>
        <span @click='numberPressed'>1</span>
        <span @click='numberPressed'>2</span>
        <span @click='numberPressed'>3</span>
        <span @click='equalPressed' class="operator" id="equals">=</span>
        <div class="l-row">
          <span @click='numberPressed' id="zero">0</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  data() {
    return{
      screenValue: "",
    }
  },
  methods: {
    numberPressed: function() {
      this.screenValue += event.target.innerText
    },
    operatorPressed: function(){
      if(!"*/+-".includes(this.screenValue[this.screenValue.length - 1])) {
        this.screenValue += event.target.innerText
      }
    },
    dividePressed: function() { 
      if(!"*/+-".includes(this.screenValue[this.screenValue.length - 1])) {
        this.screenValue += "/"
      }
    },
    clearPressed: function() {
      this.screenValue = ""
    },
    equalPressed: function() {
      this.screenValue = `${eval(this.screenValue)}`
    },
    
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#calculator {
  background: #2B3D50;
  border-radius: 10px;
  padding: 15px;
  width: 335px;
  margin-left: auto;
  margin-right: auto;
}

#screen-container {
  background: #5E626D;
  border-radius: 10px;
  padding: 20px;
}

#screen {
  background: rgb(239, 217, 93);
  border: none;
  font-family: 'Orbitron', sans-serif;
  font-size: 1.4em;
  font-weight: 600;
  height: 23px;
  overflow: hidden;
  padding: 12px 15px;
  width: 265px;
  z-index: 1;
}

#zero {
  width: 225px;
}

#clear {
  background: rgb(207, 67, 67);
  width: 147px;
}

#clear:active {
  background-color: #E67E22;
}

#equals {
  height: 89px;
}

#buttons-container {
  padding: 30px 0 0 15px;
}

.l-row {
  position: absolute;
  top: 353px;
}

.buttons {
  overflow: hidden;
}

.buttons span {
  background: rgb(146, 137, 207);
  border-radius: 20px;
  border: none;
  box-shadow: inset 0px 1px 0px #5E626D, 0px 5px 0px 0px #45637F;
  cursor: pointer;
  float: left;
  font-family: 'Oswald', sans-serif;
  width: 70px;
  height: 40px;
  margin: 0 7px 11px 0;
  line-height: 40px;
  text-align: center;
}

.buttons span:active {
  background-color: #4AA3DF;
  top: 3px;
  box-shadow: inset 0px 1px 0px #5E626D, 0px 2px 0px 0px #45637F;
}

.operator {
  font-size: 1.3em;

}
</style>

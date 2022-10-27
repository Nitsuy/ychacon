<script lang="ts">
import { ref } from 'vue'

const count = ref(0)

export default{
  data(){
    return{
      varD: 0,
      varE: 0,
      varS: 0,
      current: 0,
      toggle: true,
    }
  },
  methods: {
    clear(){
      this.current = 0;
    },
    varDevelop(numD: number){
      this.varD = numD;
      this.toggle = !this.toggle;
    },
    varEmissions(numE: number){
      this.varE = numE;
      this.toggle = !this.toggle;
    },
    varSustain(numS: number){
      this.varS = numS;
      this.toggle = !this.toggle;
    },
    result(){
      this.current = (this.varD * this.varE) - this.varS;
    },

  }


}
</script>

<template>
  <div>

  </div>
  
  <div class="calculator"> 
    <div class="variables">Development</div>
    <div @click="varDevelop(1)" class="btn">1</div>
    <div @click="varDevelop(2)" class="btn">2</div>
    <div @click="varDevelop(3)" class="btn">3</div>
    <div class="variables">Greenhouse Gas Emission</div>
    <div @click="varEmissions(1)" class="btn">1</div>
    <div @click="varEmissions(2)" class="btn">2</div>
    <div @click="varEmissions(3)" class="btn">3</div>
    <div class="variables">Sustainable Energy Sources</div>
    <div @click="varSustain(1)" class="btn">1</div>
    <div @click="varSustain(2)" class="btn">2</div>
    <div @click="varSustain(3)" class="btn">3</div>
    <div class="variables">Climate Impact</div>
    <div class="display">{{current || '0'}}</div>
    <div @click="result" class="btn">=</div>
  </div>
  <h1>trying stuff out</h1>

  <div class="card">
    <button type="button" @click="">The country gets a ranking of: {{ current }}</button>


    <p>
      <code>Select the values for each variable and then click on the "=" button to show the country's climate impact!</code>
    </p>
  </div>

  <div>Low Contaminating: 0-3</div>
  <div>Medium Contaminating: 3-6</div>
  <div>Highly Contaminating: 6-8</div>

</template>


<style scoped>
.read-the-docs {
  color: #888;
}
.calculator{
  margin: 0 auto;
  width: 600px;
  font-size: 20px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
  border: 1px solid #333;
}

.display{
  grid-column-end: 1/3;
  background-color: black;
  color: white;
}

.btn{
  border: 1px solid #333;
  background-color: white;
  color: #333;
}

.variables{
  border: 1px solid #333;
  background-color: darkorange;
  color: white;
}
</style>

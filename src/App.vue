<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png"><br>
    <button v-if="!isStarted" @click="isTest = true, isStarted = true, firstQuestion()" class="btn">Start</button>
    <Test 
        v-else-if="isTest" 
        @res="mark = $event" 
        :isTest="true"
        :q = Question
        :qCounter = counter
        @testFalse="isTest = $event"/>
    <Result v-else :mark="mark"/>  
  </div>
</template>

<script>

import Test from './components/Test.vue'
import Result from './components/Result.vue'
export default {
  name: 'App',
  // props:['mark'],
  data(){
    return{
      isStarted: false,
      isTest: false,
      mark: 0,
      counter: 0,
      Question: 0
    }
  },
  methods:{
    result: function(){
      console.log(this.mark);
  },
  firstQuestion: function() {
    this.Question = Math.floor(Math.random() * (185 - 0) + 0);
    this.counter++;
    console.log(this.Question);
  }
    
  },
  components: {
    Test,
    Result
  },
  computed:{
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
img{
  width: 150px;
  height: 150px;
}

</style>

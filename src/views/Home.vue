<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
   <div class="counter"
   :style="{color:$store.state.colorCode}"
   >
    {{$store.state.counter}}
   </div>
   <div class="counterSquared">
    <sup>2</sup>=
    {{$store.getters.counterSquared}}
   </div>
    <div class="buttons">
       <button @click="$store.dispatch('increaseCounter')">+</button>
   <button @click="$store.dispatch('decreaseCounter')">-</button> 
   <input type="text" placeholder="enter color" v-model="colorCode">
    <!-- using commit method -->
    <!-- <button @click="$store.commit('increaseCounter')">+</button>
   <button @click="$store.commit('decreaseCounter')">-</button> -->
   
   </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    
  },
  computed:{
    colorCode:{
    get(){
    return this.$store.state.colorCode
    },
    set(newValue){
    this.$store.commit('setColorCode',newValue)
    }
  }
  }
}
</script>
<style>

.buttons button{
  margin-bottom: 10px;
  font-size: 40px;
  margin: 0px 10px;
}
</style>

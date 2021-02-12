<template>
  <div class="home">
    <bomb-amount @set-amount="changeAmount"></bomb-amount>
    <Deactivate @stop-bombs="deactivateBombs" v-if="deactivate"/>
    <div class="flex">
      <bomb-set v-for="(bomb, id) in bombsAmount" :key="id" :id="id" @is-active="activating" :stop="stopActive"></bomb-set>
    </div>
    
  </div>
</template>

<script>
// @ is an alias to /src
import Deactivate from '@/components/Deactivate.vue'
import BombSet from '../components/BombSet.vue'
import BombAmount from '../components/BombAmount.vue'

export default {
  name: 'Home',
  components: {
    Deactivate,
    BombSet,
    BombAmount
  },
  data() {
    return { 
      areActive:0,
      bombsAmount: 0,
      deactivate:false,
      stopActive: false
      }
  },
  methods: {
    deactivateBombs() {
      this.stopActive = true;
    },
    changeAmount(amount) {
      this.bombsAmount = Number(amount);
      console.log("Amount is changed: " + this.bombsAmount)
    },
    activating() {
      this.areActive++;
      if (this.areActive == this.bombsAmount){
        this.deactivate = true;
      }
    }
  }
}
</script>
<style>
  .flex{
    display: flex;
  }
</style>
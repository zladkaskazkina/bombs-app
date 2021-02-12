<template>
  <div class="container" v-if="!exploded" >
    <Bomb></Bomb>
    <button v-if="!isActive" @click="activateBomb">Activate</button>
    <h3 v-if="isActive"> {{ countdown }} </h3>
  </div>
</template>

<script>
import Bomb from "./Bomb.vue";
export default {
  emits:["is-active"],
  props:["id", "stop"],
  components: {
    Bomb
  },
  data() {
    return {
      countdown: 0,
      isActive: false,
      exploded: false
    }
  },
  watch: {
    countdown: {
      handler(value) {
         if (value > 0 && this.stop!==true) {
             setTimeout(() => {
                 this.countdown--;
             }, 1000);
         } else if(value > 0 && this.stop===true){
            this.isActive = false;
         } else {
           this.exploded = true;
         }
        },
    }
  },
  methods: {
    activateBomb() {
      this.isActive = true;
      this.countdown = 5;
      this.$emit("is-active");
    }
  },

}
</script>

<style>
.container {
  margin: 3rem;
}
</style>
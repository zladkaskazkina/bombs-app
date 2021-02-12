<template>
  <div class="bombs">
    <h3>Zadejte pocet bomb</h3>
    <input type="text" v-model="amountOfBombs">
    <button @click="setBombs">Potvrdit</button>
  </div>
</template>

<script>
export default {
  emits:['set-amount'],
  data() {
    return {
      amountOfBombs: "",
    }
  },
  methods: {
    setBombs() {
        this.$emit('set-amount', this.amountOfBombs);
    }
  }
}
</script>
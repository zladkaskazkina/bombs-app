<template>
  <div class="deactivate">
    <button @click="deactivate">Zneskodnit</button>
  </div>
</template>

<script>
export default {
  emits:["stop-bombs"],
  data(){
    return {}
  },
  methods: {
    deactivate() {
      this.$emit("stop-bombs");
    }
  }
}
</script>

<style>
.deactivate {
  margin-top: 2rem;
}
</style>
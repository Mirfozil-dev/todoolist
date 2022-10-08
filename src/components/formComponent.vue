<template>
  <div>
    <input type="text" :value="query" @input="inputQuery" @keyup.enter="$emit('onSave')">
    <button @click="$emit('onSave')">save</button>
  </div>
</template>

<script>
export default {
  name: "formComponent",
  props: ['query'],
  methods: {
    inputQuery(event) {
      this.$emit('onInput', event.target.value)
      // console.log(event.target.value)
    }
  }
}
</script>

<style scoped>

</style>
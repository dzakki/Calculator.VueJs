<template>
  <div class="container">
      <h1 class="title">
        calculator
      </h1>
      <calculator></calculator>
  </div>
</template>

<script>
import calculator from "~/components/Calculator.vue"
export default {
  components: {
  	calculator,
  },
}
</script>
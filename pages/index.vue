<template>
  <div class="container">
    {{greeting}}
    {{flaskGreeting}}
  </div>
</template>

<script>
export default {
  components: {
  },
  data: function () {
    return {
      greeting: "Hello Vue !",
      flaskGreeting: ""
    }
  },
  created: async function () {
    const gResponse = await fetch("http://127.0.0.1:5000/greeting");
    const gObject = await gResponse.json()
    this.flaskGreeting=gObject.greeting
  }
}
</script>

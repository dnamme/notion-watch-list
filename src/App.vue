<template>
  <Random />
</template>

<script>
import Random from "./components/random/Random.vue";

export default {
  name: "App",
  components: {
    Random,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap");

* {
  font-family: "Poppins", sans-serif;
  font-size: 16px;
}

h1 {
  font-size: 67.34px;
}

h2 {
  font-size: 50.52px;
}

h3 {
  font-size: 37.9px;
}

h4 {
  font-size: 28.43px;
}

h5 {
  font-size: 21.33px;
}

h6 {
  font-size: 16px;
}
</style>

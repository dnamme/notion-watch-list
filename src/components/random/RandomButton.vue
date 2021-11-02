<template>
  <button @click="onClick()"><h5>Random</h5></button>
</template>

<script>
export default {
  name: "RandomButton",
  methods: {
    onClick() {
      console.log("random");
    },
  },
};
</script>

<style scoped>
#random-button {
  background-color: rgba(255, 255, 255, 0.35);
  padding: 8px 24px;
  border-radius: 8px;
  border: none;
  color: white;

  cursor: pointer;
}

h5 {
  margin: 0;
}
</style>

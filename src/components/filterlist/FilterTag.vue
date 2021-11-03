<template>
  <button class="selected" v-if="isSelected === true" @click="_onClick()">
    {{ text }}
  </button>

  <button class="selected" v-else @click="_onClick()">
    {{ text }}
  </button>

  <!-- <button @click="_onClick()">
    {{ text }} -->
  <!-- <FaCheck v-if="isSelected == true" />
    <FaTimes v-else /> -->
  <!-- </button> -->
</template>

<script>
// import { library } from "@fortawesome/fontawesome-svg-core";
// import { faCheck, faTimes } from "@fortawesome/free-solid-svg-icons";
// library.add(faCheck, faTimes);

export default {
  name: "FilterTag",
  props: {
    text: {
      default: "Tag",
      type: String,
    },
    isSelected: {
      default: true,
      type: Boolean,
    },
    onClick: Function,
  },
  methods: {
    _onClick() {
      if (this.onClick != null) this.onClick();
      else console.log(`clicked ${this.text}`);
    },
  },
  components: {
    // faCheck,
    // faTimes,
  },
};
</script>

<style scoped>
button {
  cursor: pointer;

  border: 1px solid white;
  border-radius: 32px;

  padding: 4px 24px 4px 24px;
  margin: 0 16px 16px 0;

  background-color: transparent;
  color: white;
}

button.selected {
  border: 1px solid #33b679;

  color: #33b679;
}
</style>

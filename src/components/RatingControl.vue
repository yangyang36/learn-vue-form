<template>
  <ul>
    <li :class="{ active: modelValue === 'Low' }">
      <button type="button" @click="activate('Low')">Low</button>
    </li>
    <li :class="{ active: modelValue === 'Normal' }">
      <button type="button" @click="activate('Normal')">Normal</button>
    </li>
    <li :class="{ active: modelValue === 'Rich' }">
      <button type="button" @click="activate('Rich')">Rich</button>
    </li>
  </ul>
</template>
<script>
export default {
  //custom component with V-model
  props: ['modelValue'],
  emits: ['update:modelValue'],

  //data() {
  //  return {
  //    activeOption: null,
  //  };
  //},
  methods: {
    activate(option) {
      //this.activeOption = option;
      this.$emit('update:modelValue', option);
    },
  },
};
</script>
<style scoped>
.active {
  border-color: #a00078;
}
.active button {
  border-color: #a00078;
}
ul {
  list-style: none;
  margin: 0.5rem 0;
  padding: 0;
  display: flex;
}
li {
  margin: 0 1rem;
  border: 1px solid #ccc;
  padding: 1rem;
  display: flex;
  justify-content: center;
  align-content: center;
}
button {
  font: inherit;
  border: none;
  background-color: transparent;
  cursor: pointer;
}
</style>

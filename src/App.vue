<template>
  <div>
    <h1 :class="{ active: isActive }" :style="{ color: activeColor }">
      Welcome sir
    </h1>
    <input type="text" @input="updateText" :class="{ error: hasError }" placeholder="Enter some text">
    <p>You entered: {{ text }}</p>
    <button @click="toggleActive">Tekan</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: true,
      activeColor: 'red',
      text: '',
      hasError: false
    }
  },
  methods: {
    updateText(event) {
      this.text = event.target.value
      this.hasError = !this.text
    },
    toggleActive() {
      this.isActive = !this.isActive
      this.activeColor = this.isActive ? 'red' : 'blue'
    }
  }
}
</script>

<style scoped>
.active {
  background-color: rgb(0, 0, 0);
}

.error {
  border: 1px solid red;
}

button {
  background-color: blue;
  color: white;
  padding: 5px 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
</style>
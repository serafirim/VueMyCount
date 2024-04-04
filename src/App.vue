<template>
  <div id="app">
    <h1>Count Text Length</h1>
    <p><input type="text" v-model="inputText" /></p>
    <CharCount :params="charCountParams"></CharCount>
    <p><button @click="reset()">Reset</button></p>
  </div>
</template>

<script lang="ts">
//https://www.vuemastery.com/blog/getting-started-with-typescript-and-vuejs/
import { defineComponent } from 'vue'
import CharCount, { CharCountParams } from './components/CharCount.vue'

// ADD STATE
interface State {
  inputText: string
}

export default defineComponent({
  name: 'App',
  components: { 
    CharCount 
  },
  data: (): State => {
    return { inputText: '' }
  },
  methods: {
    reset() {
      this.inputText = ''
    }
  },
  computed: {
    charCountParams(): CharCountParams {
      return {
        inputText: this.inputText,
        label: 'Count'
      }
    }
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

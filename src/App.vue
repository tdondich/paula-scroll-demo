<template>
  <div id="app">
    <chat-viewer :log="log" />
    <input-handler @updated="handleInput" />
  </div>
</template>

<script>
import chatViewer from './components/chatviewer'
import inputHandler from './components/inputhandler'

export default {
  name: 'ChatExample',
  components: {
    'input-handler': inputHandler,
    'chat-viewer': chatViewer
  },
  data: function () {
    return {
      log: [],
      maxScrollBack: 5
    }
  },
  methods: {
    handleInput (text) {
      this.log.push(text)
      // @todo Handle cap of maximum number of items to render
      if (this.log.length > this.maxScrollBack) {
        // Pop from the beginning
        this.log.shift()
      }
    }
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>

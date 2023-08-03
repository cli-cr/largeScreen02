<template>
  <div id="app">
    <Screen></Screen>
  </div>
</template>

<script>
import Screen from './components/Screen.vue'

export default {
  name: 'App',
  components: {
    Screen
  },
  mounted() {
    this.initWebsocket()
  },
  
  methods: {
    initWebsocket() {
      const ws = new WebSocket("ws://82.157.123.54:9010/ajaxchattest")
      ws.onopen = function(){
        alert("websocket连接成功")
      }
      ws.onerror = function(){
        alert("websocket连接失败")
      }
      ws.onmessage = msg => {
        console.log(msg);
      }
    },
  },
}
</script>

<style>

</style>

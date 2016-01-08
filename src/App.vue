<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <h2>{{ f1}}</h2>
  </div>
</template>

<script>
import { Socket } from "phoenix_js";

export default {
  props:["f1"],
  ready(){
    console.log("hello from component");
        let socket = new Socket("/socket");
        socket.connect();
        let channel = socket.channel("rooms:myroom", {})
        channel.join()
          .receive("ok", resp => { console.log("Joined successfully", resp) })
          .receive("error", resp => { console.log("Unable to join", resp) });

        channel.push("new_msg", {body: "testing"});
        channel.on("new_msg", payload => {
          console.log(payload);
          this.msg=payload.body;
})
  },
  data () {
    return {
      msg: 'Hello Vues!'
    }
  }
}
</script>


<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
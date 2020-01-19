<template>
  <div>
    <!-- <hello msg="hello vue js"></hello>
    <button @click="great('hello vue')">hello vue</button>
    <input :value="message" type="text" @input="handleInput"/><span>{{message}}</span>
    <input v-model="message" />
    {{message}}
    <rand></rand>
    <div>{{httpMessage}}></div>
    <Computed></Computed>
    <Watch></Watch>
    <Clock></Clock> -->
    <Command></Command>
  </div>
</template>

<script>
// import Hello from "./components/Hello.vue";
// import rand from "./components/rand.vue";
import axios from "axios";
// import Computed from "./components/Computed.vue";
// import Watch from "./components/Watch.vue";
// import Clock from "./components/Clock.vue"
import Command from "./components/Command.vue"

export default {
  name: "app",
  components: {
    // Hello,
    // rand,
    // Computed,
    // Watch,
    Command
  },
  methods: {
    great: function(message) {
      alert(message);
    },
    handleInput: function(e) {
      this.message = e.target.value;
    }
  },
  data() {
    return {
      message: "aaa",
      httpMessage: ""
    };
  },
  mounted() {
    axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then(response => (this.httpMessage = response));
  }
};
</script>


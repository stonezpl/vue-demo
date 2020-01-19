<template>
  <div>
    <h2 v-text="message">hello</h2>

    <div v-html="'<span style=&quot;color: red&quot;>hello vue</span>'">hello world</div>

    <div v-show="show">show...</div>
    <button @click="show = !show">change show</button>
  </div>
</template>

<script>
export default {
  data: function() {
    this.log = window.console.log;
    return {
      show: true,
      number: 1,
      message: "world"
    };
  }
};
</script>
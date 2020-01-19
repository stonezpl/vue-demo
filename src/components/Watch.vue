<template>
  <div id="watch-example">
    <p>
      Ask a yes/no question:
      <input v-model="question" />
    </p>
    <p>{{ answer }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      question: "",
      answer: "I cannot give you an answer until you ask a question!"
    };
  },
  watch: {
    question: function() {
      this.answer = "waitting...";
      this.getAnswer()
    }
  },
  methods: {
    getAnswer: function() {
      if (this.question.indexOf("?") === -1) {
        this.answer = "Questions usually contain a question mark. ;-)";
        return;
      }
      this.answer = "Thinking";
      var vm = this;
      axios
        .get("https://yesno.wtf/api")
        .then(function(response) {
          vm.answer = response.data.answer;
        })
        .catch(function(error) {
          vm.answer = "Error! Could not reach the API. " + error;
        });
    }
  }
};
</script>
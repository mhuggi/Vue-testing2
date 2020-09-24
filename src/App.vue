<template>
  <div id="app">
    <Header />
    <Quiz @answered="checkA" :currentQ="questions[current]" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Quiz from "./components/Quiz.vue";


export default {
  name: 'App',
  components: {
    Header,
    Quiz
  },
  methods: {
    checkA(a) {
      if (a == this.questions[this.current].c) {
        alert("Rätt svar!")
        this.current += 1
      } else {
        alert("Försök igen")
      }
      }
  },
  data: function() {
    return {
      questions: [
        {
          q: "Hur går det?",
          a: ["Bra", "Dåligt", "Semi"],
          c: 2
        },
        {
          q: "Allt bra?",
          a: ["Joo", "Jaa", "Buu"],
          c: 0
        }
      ],
      current: 0 
    }

  }
}
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

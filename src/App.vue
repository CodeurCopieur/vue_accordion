<template>
  <div id="app">
    <header>
      <h1>The Vue<span>cordion</span></h1>
    </header>
    <section class="faqs">
      <Faq 
        v-for="(faq, i) in faqs" 
        :key="i" 
        :faq="faq" 
        :index="i"
        :open="faq.open"
        @toggleOpen="toggleOpen" />
    </section>
  </div>
</template>

<script>
import Faq from './components/faqs.vue'

export default {
  name: 'App',
  components: {
    Faq
  },
  data() {
    return {
      faqs: [
        {
          question: "Who is the best Superhero?",
          answer: "I'm not sure but we love him 3000",
          open: false
        },
        {
          question: "What is Goku's form called with White Hair?",
          answer: "Mastered Ultra Instinct",
          open: false
        },
        {
          question: "Have you liked & subscried yet?",
          answer: "YES",
          open: false
        }
      ]
    }
  },
  methods: {
    toggleOpen (index) {
      this.faqs = this.faqs.map( (faq, i) => {
        if(index === i) {
          faq.open = !faq.open
        }
        return faq;
      })
    }
  }
}
</script>

<style lang="scss">
*, ::before, ::after{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-color: #EEE;
}

header {
  background-color: #35495E;
  padding: 15px;
  display: flex;
  justify-content: center;
  align-items: center;

  h1 {
    color: #FFF;
    font-size: 28px;
    font-weight: 300;
    text-transform: uppercase;

    span {
      color: #41B883;
      font-weight: 900;
    }
  }
}

.faqs {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
</style>

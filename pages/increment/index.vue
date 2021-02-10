<template>
  <div>
    <title-stisla title="Coba increment" />
    <skeleton>
      <div id="watch-example">
        <p>
          Ask a yes/no question:
          <input v-model="question">
        </p>
        <p>{{ answer }}</p>
      </div>

      <div class="text-right mt-2 mr-2">
        <button class="btn btn-secondary" @click="minus">
          <i class="fas fa-minus" />Decrement
        </button>
        <button class="btn btn-primary" @click="add">
          <i class="fas fa-Plus" />Increment
        </button>

        <div class="d-flex justify-content-center h-100">
          <div class="d-flex align-items-center">
            <!-- <h1>{{ increment == 3 ? "Terlalu Banyak" : increment }}</h1> --> <!--seperti ini bisa cuma untuk mengurangi logic disin imaka p[ake computed-->
            <h1>{{ computedIncrement }}</h1>
          </div>
        </div>
      </div>
    </skeleton>
  </div>
</template>

<script>
export default {
  layout: 'admin',

  data () {
    return {
      increment: 0,
      question: '',
      answer: 'Questions usually contain aquestion mark. ;-)'
    }
  },

  computed: {
    computedIncrement () {
      return this.increment === 3 ? 'Increment terlalu banyak' : this.increment
    }
  },
  watch: {
    // whenever question changes, this function will run
    question (newQuestion, oldQuestion) {
      if (newQuestion.includes('?')) {
        this.getAnswer()
      }
    }
  },

  methods: {
    add () {
      if (this.increment < 3) { this.increment++ }
    },
    minus () {
      if (this.increment > 0) { this.increment-- }
    },

    getAnswer () {
      this.answer = 'Thinking...'
      this.$axios
        .get('https://yesno.wtf/api')
        .then((response) => {
          this.answer = response.data.answer
        }).catch((error) => {
          this.answer = 'Error! Could not reach the API. ' + error
        })
    }

  }
}
</script>

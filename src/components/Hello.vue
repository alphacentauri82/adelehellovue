<template>
  <div>
    <div v-if="!lost">
      <div v-if="questions.length">
        <blockquote class="col-sm-8 col-sm-offset-2">
          <h5>{{getQuestion}}</h5>
          <small>Adele</small>
        </blockquote>
        <div class="align-center">
          <div @click="next" class="btn btn-success">{{getCorrect}}</div>
          <div @click="lose" class="btn btn-default">{{getIncorrect}}</div>
        </div>
      </div>
      <div v-if="!questions.length">
        <h4>Adele loves Vue!</h4>
        <img src="https://s-i.huffpost.com/gen/3703954/images/n-ADELE-628x314.jpg" alt="You won">
      </div>
    </div>
    <div v-if="lost">
      <h4>May Adele set you on fire (and the rain too)</h4>
      <img src="http://i.dailymail.co.uk/i/pix/2015/12/15/07/2F63250700000578-3360463-image-a-18_1450165003316.jpg" alt="You lost">
    </div>
  </div>
</template>

<script>
  export default {
    name: 'hello',
    data () {
      return {
        lost: false,
        questions: [
          {
            message: `Hello, it's me. I was wondering if after all these years you'd like to meet`,
            correct: 'Sure',
            incorrect: 'No way rain pyro'
          },
          {
            message: `To go over everything`,
            correct: `Let's do this together`,
            incorrect: 'Maybe not?'
          },
          {
            message: `They say that time's supposed to heal ya, But I ain't done much healing`,
            correct: '*hug*',
            incorrect: '*You'
          },
          {
            message: `Hello, can you hear me?`,
            correct: 'Yes',
            incorrect: `Yes but i'm not answering`
          },
          {
            message: `I'm in California dreaming about who we used to be, when we were younger and free`,
            correct: 'Going',
            incorrect: `Going but without you`
          },
          {
            message: `I've forgotten how it felt before the world fell at our feet`,
            correct: 'We were together',
            incorrect: `Maybe the floor collapsed`
          },
          {
            message: `There's such a difference between us and a million miles`,
            correct: 'We can adapt',
            incorrect: `Moving far away`
          },
          {
            message: `Hello from the other side, I must have called a thousand times`,
            correct: 'Sorry, phone on the other trousers',
            incorrect: `Adeleted you from my phone`
          },
          {
            message: `To tell you I'm sorry for everything that I've done, but when I call you never seem to be home`,
            correct: 'I forgive you',
            incorrect: `Stop spamming`
          }
        ]
      }
    },
    methods: {
      next () {
        this.questions.splice(0, 1)
      },
      lose () {
        this.lost = true
      }
    },
    computed: {
      getQuestion () {
        return this.questions[0].message
      },
      getCorrect () {
        return this.questions[0].correct
      },
      getIncorrect () {
        return this.questions[0].incorrect
      }
    }
  }
</script>

<style scoped>
  p {
    color: forestgreen;
  }

  blockquote {
    text-align: center;
    float: none;
    border: none;
  }
</style>

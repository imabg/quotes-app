<template>
    <div class="container">
      <h1>Quotes-Application</h1>
      <myheader :quotesCount = "quotes.length" :maxLength = "maxLength"></myheader>
      <newQuote @quoteAdded = "addQuote"></newQuote>
      <quotesGrid :quotes = "quotes" @deletedQuote = "deleteQuote"></quotesGrid>
      <myFooter></myFooter>
    </div>
</template>

<script>
import myheader from './components/myheader.vue';
import quotesGrid from './components/quotesGrid.vue';
import newQuote from './components/newQuote.vue';
import footer from './components/footer.vue';

export default {
  name: 'app',
  data() {
    return {
      quotes: [
        'Default one'
      ],
      maxLength: 10
    };
  },
  components: {
    myheader,
    quotesGrid,
    newQuote,
    myFooter: footer
  },
  methods: {
    addQuote(query) {
      if (this.quotes.length >= this.maxLength) {
        alert('Please Delete Some Quotes first!');
      }
      this.quotes.push(query);
    },
    deleteQuote(index) {
       this.quotes.splice(index, 1);
    }
  }
}
</script>

<style scoped>
  h1 {
    margin-top: 15px;
    text-align: center;
  }
</style>

<template>
  <div class="home">
    <new-quote @quoteAdded="newQuote"></new-quote>
    <quote-grid :quotes="quotes"></quote-grid>
  </div>
</template>

<script>
// @ is an alias to /src
import QuoteGrid from '@/components/QuoteGrid';
import NewQuote from '@/components/NewQuote';

export default {
  name: 'home',
  data() {
    return {
      quotes: ['A simple quote'],
      maxQuotes: 10
    };
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    }
  },
  components: {
    QuoteGrid,
    NewQuote
  }
};
</script>

<style lang="scss" scoped>
  .home {
    margin-top: 20px;
  }
</style>


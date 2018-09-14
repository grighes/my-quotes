<template>
  <div class="home container">
    <Header  :quoteCount="quotes.length" :maxQuotes="maxQuotes" />
    <new-quote @quoteAdded="newQuote"></new-quote>
    <quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></quote-grid>
  </div>
</template>

<script>
// @ is an alias to /src
import QuoteGrid from '@/components/QuoteGrid';
import NewQuote from '@/components/NewQuote';
import Header from '@/components/Header';

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
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    QuoteGrid,
    NewQuote,
    Header
  }
};
</script>

<style lang="scss" scoped>
.home {
  margin-top: 20px;
}
</style>


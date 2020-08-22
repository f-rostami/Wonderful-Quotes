<template>
  <div id="app" class="container">
    <app-header :maxQuotes="maxQuotes" :quoteCount="quotes.length"></app-header>
    <app-new-quote @quoteAdded="addNewQuote($event)"></app-new-quote>
    <app-quote-grid
      :quotes="quotes"
      @quoteDeleted="deleteQuote($event)"
    ></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info : Click on a Quote to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data: function() {
    return {
      quotes: ["Hust a Quote to see something"],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header
  },
  methods: {
    addNewQuote(newQuote) {
      if (this.quotes.length >= this.maxQuotes)
        return alert("Please delete quote first.");
      this.quotes.push(newQuote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style></style>

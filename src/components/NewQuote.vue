<template>
  <div class="container">
    <form>
      <div class="form-group row">
        <h3>Add Quote</h3>
        <textarea class="form-control" rows="3" v-model="quote"></textarea>
      </div>
      <div class="form-group row">
        <div class="col-md-0">
          <button class="btn btn-primary" @click.prevent="createNew">
            Add Quote
          </button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: ''
    };
  },
  methods: {
    createNew() {
      this.$emit('quoteAdded', this.quote);
      this.quote = '';
    }
  }
};
</script>

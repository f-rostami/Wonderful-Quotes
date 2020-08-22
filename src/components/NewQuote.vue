<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <textarea class="form-control" rows="3" v-model="quote"> </textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
        <button @click.prevent="createNew()" class="btn btn-primary">
          Add Quote
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      quote: ""
    };
  },
  methods: {
    createNew() {
      if (this.quote == "") return alert("Please type quote first.");
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style></style>

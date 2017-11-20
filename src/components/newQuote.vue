<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label>Quote</label>
        <textarea class="form-control" rows="3" v-model="quote"></textarea>
      </div>

      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
      </div>
    </form>
  </div>
  <!-- /.container -->
</template>

<script>
  export default {
    data () {
      return {
        quote: ''
      }
    },
    methods: {
      createNew () {
        if (this.quote.length > 0) {
          this.$emit('quoteAdded', this.quote)
          this.quote = ''
        } else {
          return alert('Your quote not have a text! Please add some text.')
        }
      }
    }
  }
</script>

<style>

</style>

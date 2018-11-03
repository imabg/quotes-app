<template>
  <div class="row">
    <appQuote v-for = "(quote, index) in quotes"  @click.native = "deleteQuote(index)" :key = "index">
      {{quote}}
    </appQuote>
  </div>
</template>

<script>
import quote from './quote.vue';
export default {
  name: 'quotesGrid',
  props: ['quotes'],
  components: {
    appQuote: quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit('deletedQuote', index);
    }
  }
}
</script>

<style>
</style>

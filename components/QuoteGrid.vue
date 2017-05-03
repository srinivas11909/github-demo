<template>
  <div class="row">
     <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)"> {{ quote }} </app-quote>
  </div>
</template>
<script>
import Quote from './Quote.vue';

    export default {
       props: ['quotes'],
       methods: {
         deleteQuote(index) {
             this.$emit('quoteDeleted', index);
         }
       },
       components: {
         appQuote : Quote
       }
    }
</script>
<style>
  .panel-body{font-family: 'Arizonia', cursive;font-size: 24px;color: #6e6e6e;}
  .quote{cursor: pointer;}
  .quote:hover{background-color: #ffe2e2}
</style>

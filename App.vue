<template>
  <div class="container">
    <router-view></router-view>
    <app-navigation></app-navigation>
    <app-header :quoteCount="quotes.length" :maxquotes="maxquotes"></app-header>
    <app-new-todo @addTodo="newTodo"></app-new-todo>
    <app-todo-grid :todos="todos"></app-todo-grid>
    <app-new-quote @addQuote="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Navigation from './components/Navigation.vue';
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import NewTodo from './components/NewTodo.vue';
import TodoGrid from './components/TodoGrid.vue';
  export default {
    data: function(){
      return{
        quotes:[
          'First Quote gei it so hard'
        ],
        todos:[
          'Add data here'
        ],
        maxquotes:10
      };
    },
    methods: {
      newQuote(quote) {
        if (this.quotes.length >=  this.maxquotes) {
            return alert('You exceed the maxquotes limit..');
        }
           this.quotes.push(quote);
      },
      deleteQuote(index) {
         this.quotes.splice(index, 1);
      },
      newTodo(todo){
        this.todos.push(todo);
      }
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote,
      appHeader: Header,
      appTodo: TodoGrid,
      appNewTodo : NewTodo,
      appTodoGrid: TodoGrid,
      appNavigation : Navigation
    }
  }
</script>

<style lang="scss">

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

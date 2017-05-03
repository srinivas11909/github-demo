<template>

  <div class="row">
    <div class="">
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
         <label>Todo</label>
         <input class="form-control" type="tesxt" v-model="todo" />
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
         <button type="button" name="button" class="btn btn-primary" @click.prevent="addTodo">Add Todo</button>
      </div>
    </div>
  </div>

</template>

<script>
export default {
   data:function(){
     return{
       todo: ''
     };
   },
   methods: {
     addTodo(){
       this.$emit('addTodo', this.todo);
       this.todo='';
       console.log(this.todo);
     }
   }
}
</script>

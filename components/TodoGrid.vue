<template>
  <div id="">
     <ul>
       <li v-for="item in todos" style="display:block"> {{ item }} </li>
     </ul>
  </div>
</template>
<script>
export default {
   props: ['todos']
}
</script>
<style>
</style>

<template>
  <div  class="row">
     <div class="col-md-12">
        <h3>Quotes Added</h3>
        <div class="progress">
          <div class="progress-bar" arial-valuenow="60" role="progressbar" arial-valuemin="0" arial-valuemax="100" :style="{width : (quoteCount / maxquotes) * 100 + '%'}">
                {{ quoteCount }} / {{ maxquotes }}
          </div>
        </div>
     </div>
  </div>
</template>
<script>
export default {
  props: ['quoteCount', 'maxquotes']
}
</script>
<style>
</style>

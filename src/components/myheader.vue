<template>
  <div class="row">
    <div class="col-sm-12">
      <h3>Quotes Added</h3>
      <div class="progress">
        <div class="progress-bar" role="progressbar" aria-valuenow = "60" aria-valuemin = "0" aria-valuemax = "100"
          :style="{width: (quotesCount / maxLength) * 100 + '%'}">
          {{quotesCount}} / {{maxLength}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'myheader',
  props: {
    quotesCount: {
      required: true
    },
    maxLength: {
      required: true
    }
  }
}
</script>

<style scoped>
  h3 {
    margin-top: 22px;
  }
</style>

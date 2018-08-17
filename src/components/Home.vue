<template>
  <div class="container">
    <div class="row">
      <div class="col-md-12">
        {{ msg }}
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Home',
  data () {
    return {
      msg: 'This is sample test task'
    }
  }
}
</script>

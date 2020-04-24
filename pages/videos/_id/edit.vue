<template>
  <div>
    Editting {{ $route.params.id }} {{video.name}}
  </div>
</template>

<script>
  export default {
    props: ['video']
  }
</script>

<style lang="scss" scoped>

</style>
<template>
  <div>
    Chúng tôi là những thứ trong video/#### {{$route.params.id}} {{video.name}}
     <nuxt-link :to="`/videos/${video.id}/edit`">
      <button>Edit</button>
     </nuxt-link>
  </div>
</template>
<script>
export default {
  props: ['video']

};
</script>

<style lang="scss" scoped>
</style>
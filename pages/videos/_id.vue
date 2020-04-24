<template>
  <div>
    <nuxt-child :video="video" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      videos: [
        {
          id: 1,
          name: "ES2015 Arrow Functions",
          description: `<p>ES2015 (aka ES6) has some great ways to make your code easier to write and understand. In this episode, we cover two different ways that you can make your code clearer by removing the 'function' keyword.</p>`,
          thumbnail:
            "https://vue-screencasts.s3.us-east-2.amazonaws.com/images/video-thumbnails/Thumbnail+-+Arrow+Function.png"
        },
        {
          id: 2,
          name: "ES2015 Template Strings",
          description: `<p>Template strings are an incredibly useful new feature in ES2015... and you can use them in your Ember apps today!</p>
                        <p>Here are 3 cool things that template strings enable.</p>`,
          thumbnail:
            "https://vue-screencasts.s3.us-east-2.amazonaws.com/images/video-thumbnails/Thumbnail+-+Template+Strings.png"
        },
        {
          id: 5,
          name: "ES2015 Modules",
          description: `<p>Before modules, javascript code loading was a mess. Now it's pretty amazing.</p>
                        <p>Learn about ES2015 modules and how they work together with ember-cli.</p>`,
          thumbnail:
            "https://vue-screencasts.s3.us-east-2.amazonaws.com/images/video-thumbnails/Thumbnail+-+ES2015+Modules.png"
        }
      ]
    };
  },
  computed: {
    video() {
      return this.videos.find(v => v.id == this.$route.params.id);
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
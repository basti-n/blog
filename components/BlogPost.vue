<template>
  <article>
    <h3>{{ blogPost.title }}</h3>
    <h6>{{ blogPost.subtitle }}</h6>
    <div v-html="$md.render(blogPost.body)" />
  </article>
</template>

<script>
export default {
  name: "BlogPost",
  props: {
    blogPost: {
      required: true,
      type: Object
    }
  }
};
</script>

<style lang="sass">
h3 {
  font-weight: bold
  color: lavender
}

h6 {
  font-style: italic
}
</style


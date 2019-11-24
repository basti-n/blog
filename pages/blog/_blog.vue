<template>
  <article>
    <h2>{{ blogPost.title }}</h2>
    <div>
      {{blogPost.body }}
    </div>
  </article>
</template>

<script>
export default {
  async asyncData({ params, payload }) {
    if (payload) {
      return { blogPost: payload };
    } else {
      return await require(`~/assets/content/blog/${params.blogPost}.json`);
    }
  }
};
</script>

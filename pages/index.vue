<template>
  <div class="container">
    <div>
      <h1 class="title">
        Miriam & Fips'ssss Blog
      </h1>
      <h2 class="subtitle">
        Food, Tri and more.
      </h2>
    </div>

    <section>
      <ul v-for="(blogPost, index) in blogPosts" :key="index">
        <nuxt-link :to="`blog/${blogPost.slug}`">{{
          blogPost.title
        }}</nuxt-link>
        <p>{{ blogPost.description }}</p>
      </ul>
    </section>
  </div>
</template>

<script>
import BlogPost from '../components/BlogPost'

export default {
  components: BlogPost,
  computed: {
    blogPosts() {
      return this.$store.state.blogPosts;
    }
  },
  head() {
    return {
      script: [
        { src: "https://identity.netlify.com/v1/netlify-identity-widget.js" }
      ]
    };
  }
};
</script>

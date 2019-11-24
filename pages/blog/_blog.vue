<template>
  <BlogPost :blogPost="blogPost"></BlogPost>
</template>

<script>
import BlogPost from "../../components/BlogPost";

export default {
  components: {BlogPost},
  async asyncData({ params, payload }) {
    if (payload) {
      return { blogPost: payload };
    } else {
      return {
        blogPost: await require(`~/assets/content/blog/${params.blog}.json`)
      };
    }
  }
};
</script>

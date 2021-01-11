<template>
  <div class="container">
    <article>
      <h1 class="title">{{ post.title }}</h1>
      <p>{{ post.body }}</p>
    </article>
    <aside>
      <h3>Posts you may also enjoy:</h3>
      <ul>
        <li v-for="related in relatedPosts">
          <nuxt-link :to="`/posts/${related.id}`">{{related.title}}</nuxt-link>
        </li>
      </ul>
    </aside>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        id: this.$route.params.id,
        posts: ''
      }
    },
    head () {
      return {
        title:  `${this.post.title} | Nuxt course on vueschool`,
        meta: [
          { name: 'twitter:title', content: this.post.title },
          { name: 'twitter:description', content: this.post.body },
          { name: 'twitter:image', content: 'https://i.imgur.com/UYP2umJ.png' },
          { name: 'twitter:card', content: 'summary_large_image' }
        ]
      }
    },
    computed: {
      post () {
        return this.$store.state.posts.all.find(post => post.id === this.id);
      },
      relatedPosts () {
        return this.$store.state.posts.all.filter(post => post.id !== this.id);
      }
    }
  }
</script>

<style scoped>
  .container {
    display: flex;
    justify-content: space-between;
    line-height: 1.5;
  }
  article * {
    margin-bottom: 1rem;
  }
  aside {
    min-width: 280px;
    max-width: 280px;
    padding-left: 2rem;
  }
  .title {
    font-size: 2rem;
  }
</style>

<template>
  <Layout>
    <Hero />
    <Categories />
    <Offers />
    <Products />
    <!-- <ul class="post-list">
      <li v-for="{ node } in $page.allWordPressPost.edges" :key="node.id">
        <Post :post="node" />
      </li>
    </ul>
    <Pager :info="$page.allWordPressPost.pageInfo"/> -->
  </Layout>
</template>

<page-query>
query Home ($page: Int) {
  allWordPressPost (page: $page, perPage: 10) @paginate {
    pageInfo {
      totalPages
      currentPage
    }
    edges {
      node {
        id
        title
        path
        excerpt
      }
    }
  }
}
</page-query>

<script>
import { Pager } from 'gridsome'
import Post from '~/components/Post.vue'
import Hero from '~/components/Hero.vue'
import Categories from '~/components/Categories.vue'
import Offers from '~/components/Offers.vue'
import Products from '~/components/Products.vue'

export default {
  components: {
    Pager,
    Post,
    Hero,
    Categories,
    Offers,
    Products
  },
  metaInfo: {
    title: 'Welcome to my blog :)'
  }
}
</script>

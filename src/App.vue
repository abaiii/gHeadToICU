<script>
  // Components
  import Bar from './components/Bar.vue'
  import Name from './components/Name.vue'
  import Posts from './components/Posts.vue'

  // JS prerequisites
  import { getPosts } from './data/posts.js'

  export default {
    components: {
      Bar,
      Name,
      Posts
    },
    data() {
      return {
        barItems: [
          { name: 'About', href: '/about.html'},
          { name: 'Built using vue-headtoall', href: 'https://github.com/franci-e/vue-headtoall'}
        ],
        postItems: getPosts()
      };
    }
  }
</script>

<template>
  <!-- Centering the title -->
  <div class="flex min-h-screen w-full justify-center items-center flex-col">
    <div class="text-4xl lg:text-6xl font-space-mono">
      <Name />
    </div>
    <div class="mt-2 font-archivo-narrow text-xl">
      <Bar
        v-for="barItem in barItems"
        :barItem="barItem.name"
        :itemHref="barItem.href"
      />
    </div>
    <div class="flex w-5/6 lg:w-2/5 mt-2 ml-2 mr-2 lg:ml-0 lg:mr-0 flex-col">
      <Posts
        v-for="postItem in postItems"
        :postDate="postItem.date"
        :postContent="postItem.content"
      />
    </div>
  </div>
</template>
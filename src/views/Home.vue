<template>
  <TopNav />
  <Banner />
  <Search />
  <Jump />
  <Hints />
  <Slogan />
  <!-- <router-link to="/search">Search</router-link> -->
</template>

<script>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import TopNav from '/Users/paul/mojeek/src/components/TopNav.vue'
import Banner from '/Users/paul/mojeek/src/components/Banner.vue'
import Search from '/Users/paul/mojeek/src/components/Search.vue'
import Jump from '/Users/paul/mojeek/src/components/Jump.vue'
import Hints from '/Users/paul/mojeek/src/components/Hints.vue'
import Slogan from '/Users/paul/mojeek/src/components/Slogan.vue'

export default {
    name: 'Home',
    components: {
        TopNav,
        Banner,
        Search,
        Jump,
        Hints,
        Slogan,
    }
}
</script>
<template>
  <header class="px-6 pt-6 pb-4 sm:py-6 lg:px-20 text-center shadow-md">
    <nav class="flex items-center flex-wrap justify-between" role="navigation">
      <div class="sm:hidden -ml-2 order-1 flex-shrink-0">
        <button
          class="flex items-center px-3 py-2 border rounded text-teal-700 border-teal-900 hover:text-gray-600 hover:border-text-gray-600"
          @click="toggle"
        >
          <svg
            class="fill-current h-3 w-3"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>
      <div
        class="w-full block flex-grow sm:flex sm:w-3/12 order-3 sm:order-1"
        :class="collapsed ? 'hidden' : ''"
      >
        <nuxt-link class="nav-link sm:w-1/2 sm:my-2" to="/">Home</nuxt-link>
        <nuxt-link class="nav-link sm:w-1/2 sm:my-2" to="/about"
          >About</nuxt-link
        >
      </div>
      <p
        class="text-xl md:text-2xl font-semibold text-teal-700 mx-auto sm:w-6/12 order-2"
      >
        {{ titleByPage() }}
      </p>
      <div
        class="w-full block flex-grow sm:flex sm:justify-center sm:w-3/12 order-4 sm:order-3"
        :class="collapsed ? 'hidden' : ''"
      >
        <nuxt-link class="nav-link sm:my-2" to="/blog">Blog</nuxt-link>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      collapsed: true
    };
  },
  methods: {
    toggle() {
      this.collapsed = !this.collapsed;
    },
    titleByPage() {
      if (this.$route.path === "/") {
        return "My portfolio";
      } else if (this.$route.path === "/blog") {
        return "My Tech-Blog";
      } else {
        return "Miguel Angel Alcala Romero";
      }
    }
  },
  watch: {
    $route() {
      this.collapsed = true;
    }
  }
};
</script>

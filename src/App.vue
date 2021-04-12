<template>
  <div id="app">
    <header>
      <MainMenu
        :tabs="tabsApp"
        @choose-tab="chooseTab"/>
    </header>
    <main>
      <router-view>

      </router-view>
    </main>
    <footer>

    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
    MainMenu: () => import('@/components/MainMenu.vue')
  },
  data () {
    return {
      tabsApp: [
        'home',
        'news',
        'history'
      ]
    }
  },
  methods: {
    chooseTab (index) {
      this.$router.push({ path: this.tabsApp[index] })
    }
  }
}

</script>

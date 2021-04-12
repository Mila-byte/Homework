<template>
  <div>
    <ul>
      <li
        v-for="(tab, index) of tabs"
        :key="index"
        @click="changeActiveTab(index)"
        :class="{active: activeTab === tab}"
        > {{ tab }} </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'MainMenu',
  props: ['tabs'],
  computed: {
    activeTab () {
      return this.$route.name
    }
  },
  methods: {
    changeActiveTab (index) {
      if (this.activeTab !== this.tabs[index]) {
        this.$emit('choose-tab', index)
      }
    }
  }
}
</script>

<style>
  li {
    cursor: pointer;
  }
  .active {
    color: red;
    cursor: auto;
  }
</style>

<template>
  <div class="tabs">
      <ul class="tab-list">
          <li
            v-for="(tab, i) in tabs"
            :class="{ active: tab.isActive }"
            :key="i">
              <a :href="tab.href" @click.prevent="selectTab(tab)">
                  {{ tab.name }}
              </a>
          </li>
      </ul>
      <div class="tabs-content">
          <slot></slot>
      </div>
  </div>
</template>
<script>
export default {
  data () {
      return {
          tabs: []
      }
  },
  created () {
      this.tabs = this.$children
  },
  mounted () {
      if (this.tabs.length > 0) {
          this.selectTab(this.tabs[0])
      }
  },
  methods: {
      selectTab (tab) {
          this.tabs.forEach(_tab => {
              _tab.isActive = (tab.href == _tab.href)
          })
      }
  }
}
</script>
<style scoped>
.tab-list {
    list-style-type: none;
    margin: 0;
    padding: 0;
}
li:first-child {
    border-top-left-radius: 20px;
}
li:last-child {
    border-top-right-radius: 20px;
}
li {
    display: inline;
    background: #007141;
    padding: 10px;
    border-right: solid 1px white;
}
a {
    text-decoration: none;
    color: white;
}
.active {
    background: #5eab5e;
}
</style>

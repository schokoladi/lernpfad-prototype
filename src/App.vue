<template>
  <div class="app">
    <side-nav v-bind:activities="activities"></side-nav>
  </div>
</template>

<script>
import SideNav from './components/SideNav'
import axios from 'axios'

export default {
  components: {
    'side-nav': SideNav
  },
  data () {
    return {
      activities: [],
      title: 'Activities'
    }
  },
  methods: {
    getActivities: function () {
      axios.get('static/activities.json')
        .then(response => {
          this.activities = response.data
        })
    }
  },
  mounted () {
    this.getActivities()
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <div id="activities">
    <h1>Activities</h1>
    <ul>
      <li v-for="activity in activities" v-bind:key="activity.id">
        <h2>{{ activity.userName }}</h2>
        <h3>{{ activity.comment }}</h3>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    activities: {
      type: Array,
      required: true
    }
  },
  data () {
    return {
    }
  }
}
</script>

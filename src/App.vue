<template>
  <div class="container" id="app">
    <h1 class="display-1">Chess Ladder</h1>
    <div class="row">
      <leaderboard v-for="r in rulesets" v-bind:key="r" v-bind:ruleset="r"></leaderboard>
    </div>
  </div>
</template>

<script>
  import Leaderboard from './components/Leaderboard';

  export default {
    name: 'app',
    components: {
      Leaderboard
    },
    data: function() {
      return {
        rulesets: process.env.VUE_APP_SOURCES
          ? process.env.VUE_APP_SOURCES.split(',')
          : ['ruleset1', 'ruleset2', 'ruleset3']
        };
    }
  }
</script>

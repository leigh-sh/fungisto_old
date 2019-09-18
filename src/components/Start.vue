<template>
  <v-layout column justify-space-around class="main-wrapper">
    <v-flex shrink>
      <v-btn color="blue lighten-4"
             @click="$emit('routeChange', 'participentSelection')">
        צור אירוע חדש
      </v-btn>
    </v-flex>
    <v-flex shrink>
      <v-btn color="deep-purple lighten-4">
        עדכן רשימת משתתפים
      </v-btn>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data: () => ({

  })
  }
</script>

<style scoped lang="stylus">
  .main-wrapper
    padding: 40px
    height: 100vh
    .v-btn
      width: 100% !important
      min-width: 100% !important
      height: 100px !important
</style>

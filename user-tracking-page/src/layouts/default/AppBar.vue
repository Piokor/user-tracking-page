<template>
  <v-app-bar flat>
    <v-spacer></v-spacer>

    <v-tabs centered color="grey-darken-2">
      <router-link to="/">
        <v-tab text="Home" rou></v-tab>
      </router-link>
      <router-link to="/stats">
        <v-tab text="Statistics"></v-tab>
      </router-link>
    </v-tabs>
    <v-spacer></v-spacer>
  </v-app-bar>
</template>

<script lang="ts" setup>
//
</script>

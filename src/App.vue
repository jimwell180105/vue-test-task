<template>
  <div>
    <template>
      <v-toolbar>
        <v-toolbar-title>Title</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items class="hidden-sm-and-down">
          <v-btn flat to="/" >Home</v-btn>
          <v-btn flat to="/list" >List</v-btn>
        </v-toolbar-items>
      </v-toolbar>
    </template>
    <router-view/>
  </div>
</template>
<script>
export default {
  name: 'App'
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

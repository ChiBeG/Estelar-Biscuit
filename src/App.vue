<template>
  <v-app>
    <v-main>
      <Navigation />
    </v-main>
  </v-app>
</template>

<script setup>
  import { useTheme } from 'vuetify'

  const theme = useTheme()

  function alterarTema(){
    theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
  }
</script>

<style>
  p{
    font-size: 100px;
  }


</style>


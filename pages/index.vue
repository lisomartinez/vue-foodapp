<template>
  <main class="container">
    <AppHeader />
    <AppRestaurantInfo :datasource="fooddata" />
  </main>
</template>

<script>
import { mapState } from 'vuex'
import AppHeader from '~/components/AppHeader'
import AppRestaurantInfo from '~/components/AppRestaurantInfo'
export default {
  components: { AppRestaurantInfo, AppHeader },
  computed: {
    ...mapState(['fooddata']),
  },
}
</script>

<style></style>

<template>
  <main class="container restaurant">
    <div class="restaurantheading">
      <h1>Restaurants</h1>
      <AppSelect @change="selectedRestaurant = $event" />
    </div>
    <AppRestaurantInfo :datasource="filteredRestaurants" />
  </main>
</template>

<script>
import { mapState } from 'vuex'
import AppRestaurantInfo from '~/components/AppRestaurantInfo'
import AppSelect from '~/components/AppSelect'
export default {
  name: 'Restaurants',
  components: { AppSelect, AppRestaurantInfo },
  data() {
    return {
      selectedRestaurant: '',
    }
  },
  computed: {
    ...mapState(['fooddata']),
    filteredRestaurants() {
      if (this.selectedRestaurant) {
        return this.fooddata.filter((el) => {
          const name = el.name.toLowerCase()
          return name.includes(this.selectedRestaurant)
        })
      } else {
        return this.fooddata
      }
    },
  },
}
</script>

<style scoped></style>

<template>
  <nav>
    <ul>
      <li>
        <nuxt-link exact to="/"><app-logo></app-logo></nuxt-link>
      </li>
      <li><nuxt-link to="/about">About</nuxt-link></li>
    </ul>
    <div v-if="cartCount > 0" class="smallnum">{{ cartCount }}</div>
    <nuxt-link to="/cart">Cart</nuxt-link>
  </nav>
</template>

<script>
import AppLogo from '@/components/AppLogo'
import { mapGetters } from 'vuex'
export default {
  name: 'AppMenu',
  components: { AppLogo },
  computed: {
    ...mapGetters(['cartCount']),
  },
}
</script>

<style lang="scss" scoped></style>

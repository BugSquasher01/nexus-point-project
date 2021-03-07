<template>
  <main class="container">
    <CarListingsGrid />
  </main>
</template>

<script>
import PlaceholderHeader from '@/components/PlaceHolderHeader.vue'
import FinanceBanner from '@/components/FinanceBanner.vue'
import CarListingsGrid from '@/components/CarListingsGrid.vue'

// import ListingFeed from '@/components/ListingFeed.vue'

export default {
  components: {
    PlaceholderHeader,
    FinanceBanner,
    CarListingsGrid
    // ListingFeed
  },
}
</script>

<style>

</style>

<template>
    <section class='carListingsMainGrid'>
        <div v-for='data in cardata' :key='data.id'>

            <!--Main listings feed grid view -->
            <div class='row'>
                <div 
                    v-for='carlisting in data.listings'
                    :key='carlisting.id'
                    class='carImage'
                    :style='`background: url(${carlisting.img}) no-repeat; max-width: 100%; height: auto;`'>

                    <!--Extra car information at bottom of each card -->
                    <div v-if='carlisting.valueYourCar' class='iteminfoContainer' >
                        <div class='itemInfo'>
                            <h3 class='carListingTitle'>{{ carlisting.item }}</h3>
                            <p class='carListingDescription'>{{ carlisting.shortDescription }}</p>
                            <p class='carListingMonthlyPrice'>£{{ carlisting.monthlyPrice }}</p>
                            <p class='carListingFullPrice'>£{{ carlisting.fullPrice }}
                            <a v-if='carlisting.calculateFinance' class='calculateFinanceLink' href='#'>Calculate Finance</a>
                            <a v-else class='calculateFinanceLink' href='#'>Calculate</a>
                            </p>
                        </div>
                    <!--End of extra car information at bottom of each card -->

                        <!-- View car button (currently not in use) -->
                        <button v-if='carlisting.viewButton' class='viewCarButton'>View</button>
                    </div>
                </div>
            </div>
            <!--End of main listings feed grid view -->
        </div>
    </section>
</template>

<script>
import { mapState } from 'vuex';

export default {
    computed: {
        ...mapState(['cardata'])
    },

};
</script>

<style>
</style>

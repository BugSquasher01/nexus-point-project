<template>
    <section class='carListingsMainGrid'>
        <div v-for='data in cardata' :key='data.id'>
            <div class='row'>
                <div 
                    v-for='carlisting in data.listings'
                    :key='carlisting.id'
                    class='carImage'
                    :style='`background: url(${carlisting.img}) no-repeat; width: 100%; height: auto;`'>

                    <div v-if='carlisting.valueYourCar' class='iteminfoContainer' >
                        <div class='itemInfo'>
                            <h3 class='carListingTitle'>{{ carlisting.item }}</h3>
                            <p class='carListingDescription'>{{ carlisting.shortDescription }}</p>
                            <p class='carListingMonthlyPrice'>£{{ carlisting.monthlyPrice }}</p>
                            <p class='carListingFullPrice'>£{{ carlisting.fullPrice }}
                            <a v-if='calculateFinance' class='calculateFinanceLink' href='#'>Calculate Finance</a></p>
                        </div>
                        <button v-if='carlisting.viewButton' class='viewCarButton'>View</button>
                    </div>
                </div>
            </div>
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

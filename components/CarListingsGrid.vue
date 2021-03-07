<template>
    <section class='carListingsMainGrid'>
        <div v-for='data in cardata' :key='data.id'>
            <!-- <h2>{{ data.name }}</h2>
            <p>Delivery Time: {{ data.deliveryTime  }}</p>
            <p>Rating: {{ data.rating }}</p>
            <p v-if='data.freeDelivery' class='label'>
                <span>Free Delivery</span>
            </p> -->

            <div class='row'>
                <div 
                    v-for='carlisting in data.listings'
                    :key='carlisting.id'
                    class='carImage'
                    :style='`background: url(${carlisting.img}) no-repeat; width: 100%; height: auto;`'>

                    <div class='iteminfo'>
                        <div>
                            <h4>{{ carlisting.item }}</h4>
                            <h5>{{ carlisting.shortDescription }}</h5>
                            <p class='itemMonthlyPrice'>£{{ carlisting.monthlyPrice }}</p>
                             <p class='itemFullPrice'>£{{ carlisting.fullPrice }}</p>
                        </div>
                        <button class='ghost'>View</button>
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
    // methods: {
    //     priceFormatting(data) {
    //         return "£" + data.toFixed(2);
    //     },
    // }
};
</script>

<style>

</style>

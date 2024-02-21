<script>
import Book from "./Book.vue";
import AboutUs from "./AboutUs.vue";

export default {
  name: "Bottom",
  components: {
    Book,
    AboutUs,
},
  data() {
    return {
        restaurants: [
                {
                    address: '1614 E. Bell Rd #104',
                    city : 'Salerno, AZ 85022',
                    number: '(602) 867-1010',
                },
                {
                    address: '204 E. Pizzetta Tommaso',
                    city : 'Sorrento, AZ 85022',
                    number: '(602) 867-1010',
                },
                {
                    address: 'Viale Puglia 54',
                    city : 'Torre Del Greco, AZ 85022',
                    number: '(602) 867-1010',
                },
                {
                    address: 'Corso Italia 20',
                    city : 'Naples, AZ 85022',
                    number: '(602) 867-1010',
                },
                
            ],
            hours: [
                {
                    days: 'monday',
                    closed: true,
                },
                {
                    days: 'tuesday untill friday',
                    hour : '9:00 - 22:00',
                },
                {
                    days: 'saturday',
                    hour : 'Saturday 11am to midnight',
                },
                {
                    days: 'sunday',
                    hour : '9:00 - 22:00',
                },
            ]
    }
  }
};
</script>

<template>
    <Book/>
    <AboutUs :restaurants="restaurants" :hours="hours"/>
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;
</style>
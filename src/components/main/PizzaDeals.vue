<script>
export default {
  name: "PizzaDeals",
  components: {
},
  data() {
        return {
            deals: [
                {
                    month: 'nov',
                    day : '02',
                    description: 'traditional neapolitan pies in kyoto pizza mercato',
                    position: '204 e. piazzetta tommaso'
                },
                {
                    month: 'nov',
                    day : '03',
                    description: 'terrazza patio dining space opening this weekend',
                    position: '204 e. piazzetta tommaso'
                },
                {
                    month: 'nov',
                    day : '05',
                    description: 'sienna private dining room with stéphane brunn',
                    position: '204 e. piazzetta tommaso'
                },
                
            ],
        };
    }
};
</script>

<template>

    <div id="deals" class="row">

<!-- left -->
        <div id="pizza-love" class="col-6 d-flex align-items-center">
            <div class="w-50 mx-auto pt-5">
                <span class="text-uppercase orange fw-bold">made with love</span>
                <h4 class="text-uppercase my-2 white">delish pizza deals</h4>

                <div v-for="(deal, index) in deals" :key="index" class="deal row pb-5 my-3 pt-4">
                    <div class="col-3">
                        <h3 class="orange mb-0 fw-bold text-center">{{ deal.day }}</h3>
                        <span class="text-uppercase white fw-bold text-center">{{ deal.month }}</span>
                    </div>
                    <div class="col-9 d-flex flex-column justify-content-center">
                        <h2 class="text-uppercase white">{{ deal.description }}</h2>
                        <div class="d-flex align-items-center gap-2">
                            <svg width="15px" height="15px" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512"><path d="M215.7 499.2C267 435 384 279.4 384 192C384 86 298 0 192 0S0 86 0 192c0 87.4 117 243 168.3 307.2c12.3 15.3 35.1 15.3 47.4 0zM192 128a64 64 0 1 1 0 128 64 64 0 1 1 0-128z"/></svg>
                            <span class="orange">{{ deal.position }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>

<!-- right -->
        <div class="col-6">
        </div>

    </div>

</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

.col-6:last-of-type{
        background-image: url(../../img/h3-img-5a.jpg);
        @include bg-cover;
    }
#pizza-love{
    background-color: $dark-gray;
    background-image: url(../../img/cielostellato.PNG);
    @include bg-cover;
    h4{
        font-size: 200%;
    }

    .deal{
        border-bottom: 2px dashed $ochre;
        h2{
            font-size: 180%;
        }
        .col-3 span{
            font-size: 160%;
            display: block;
            width: 100%;
        }
        h3{
            font-size: 350%;
        }
        svg{
            fill: $orange;
        }
    }
    .deal:last-child {
        border-bottom: none;
    }
}
</style>
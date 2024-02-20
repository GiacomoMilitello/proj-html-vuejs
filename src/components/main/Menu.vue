<script>
export default {
  name: "Menu",
  components: {
},
  data() {
        return {
            pizzas: [
                {
                    priced: '$50.00',
                    price : '$30.00',
                    name : 'bismark',
                    img: 'src/img/menu-1.png',
                    sold: false
                },
                {
                    price : '$7.00 - $50.00',
                    name : 'fiori di zucca',
                    img: 'src/img/menu-2.png',
                    sold: false
                },
                {
                    price : '$55.00',
                    name : 'valdostana',
                    img: 'src/img/menu-6.png',
                    sold: true
                },
                {
                    price : '$45.00',
                    name : 'pizza tartufata',
                    img: 'src/img/menu-4.png',
                    sold: false
                },
                {
                    price : '$25.00',
                    name : 'francescana',
                    img: 'src/img/menu-5.png',
                    sold: false
                },
                {
                    price : '$50.00 - $95.00',
                    name : 'campagnola',
                    img: 'src/img/menu-3.png',
                    sold: false
                },
            ],
        };
    }
};
</script>

<template>
    <div id="menu" class="d-flex flex-column justify-content-center align-items-center mt-5">
        <span class="text-uppercase orange fw-bold mt-5">choose your flavor</span>
        <h4 class="text-uppercase my-3">the best pizza menu in town</h4>
        <p class="w-50 text-center">Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet consequuntur ad veniam quidem qui error ea mollitia incidunt necessitatibus, fuga repellat? Maxime illum hic eius exercitationem ipsum iusto dolore neque!</p>
    </div>
    <div class="d-flex align-items-center justify-content-evenly my-5">
        <div v-for="(pizza, index) in pizzas" :key="index" class="d-flex flex-column justify-content-center align-items-center ">
            <figure>
                <img :src="pizza.img" alt="">
                <span v-if="pizza.sold" class="sold fw-bold">SOLD</span>
            </figure>
            <h5 class="mt-3 text-uppercase ">{{ pizza.name }}</h5>
            <div>
                <span v-if="pizza.priced" class="fw-bold light-ochre text-decoration-line-through">{{ pizza.priced }} - </span>
                <span class="fw-bold orange">{{ pizza.price }}</span>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;


#menu{
    h4{
        font-size: 250%;
    }
}

figure{
    position: relative;
    width: 200px;
    img{
        width: 200px
    };
    .sold{
        background-color: $orange;
        color: $white;
        font-size: 80%;
        padding: 14.25px 9.99px;
        border-radius: 50%;
        position: absolute;
        z-index: 1;
        right: 10px;
        top: 10px;
    }
}
h5{
    color: $ochre;
}

</style>
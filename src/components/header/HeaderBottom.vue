<script>
import IndicatorsCarousel from '../IndicatorsCarousel.vue';

export default {
  name: "HeaderBottom",
  components: {
    IndicatorsCarousel
},
  data() {
        return {
            ad: [
                { img : 'src/img/h3-img-1.jpg' },
                { img : 'src/img/h3-img-2.jpg' },
                { img : 'src/img/h3-img-3.jpg' },
                { img : 'src/img/h3-img-4.jpg' },
            ],
            reviews: [
                {
                    back: 'src/img/h3-testimonials-bckgrnd.jpg',
                    review: 'forget the trendy pizza shops, this hidden spot makes the best new york-style pizza slice in naples',
                    magazine: "Washington Post 2018"
                },
                {
                    back: 'src/img/h3-testimonials-bckgrnd.jpg',
                    review: 'this pizzeria serves the most authentic Neapolitan pizza in the heart of the city',
                    magazine: "The Guardian 2024"
                },
                {
                    back: 'src/img/h3-testimonials-bckgrnd.jpg',
                    review: 'a must-visit for pizza lovers, this place offers a unique twist on classic Margherita',
                    magazine: "The New York Times 2023"
                },
                {
                    back: 'src/img/h3-testimonials-bckgrnd.jpg',
                    review: 'with a perfect balance of flavors, the pizza at this place is a culinary masterpiece',
                    magazine: "The Telegraph 2022"
                },
                {
                    back: 'src/img/h3-testimonials-bckgrnd.jpg',
                    review: 'the wood-fired pizzas at this joint take you on a gastronomic journey',
                    magazine: "Los Angeles Times 2023"
                },
                {
                    back: 'src/img/h3-testimonials-bckgrnd.jpg',
                    review: 'this pizzeria, with its innovative toppings and perfect crust, sets the bar high',
                    magazine: "Chicago Tribune 2024"
                }
            ]
        };
    },
    methods: {
  openImage() {
    var svgs = document.querySelectorAll('svg');
    svgs.forEach(function(svg) {
      svg.addEventListener('click', function() {
        var imgSrc = this.nextElementSibling.src;
        var win = window.open();
        win.document.write('<img src="' + imgSrc + '" style="width: 100%; height: 100%;">');
      });
    });
  }
},
mounted() {
  this.openImage();
}
};
</script>

<template>
    <div id="advertisement" class="d-flex">
        <figure v-for="(url, index) in ad" :key="index">
            <svg height="80px" width="80px" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><path d="M288 80c-65.2 0-118.8 29.6-159.9 67.7C89.6 183.5 63 226 49.4 256c13.6 30 40.2 72.5 78.6 108.3C169.2 402.4 222.8 432 288 432s118.8-29.6 159.9-67.7C486.4 328.5 513 286 526.6 256c-13.6-30-40.2-72.5-78.6-108.3C406.8 109.6 353.2 80 288 80zM95.4 112.6C142.5 68.8 207.2 32 288 32s145.5 36.8 192.6 80.6c46.8 43.5 78.1 95.4 93 131.1c3.3 7.9 3.3 16.7 0 24.6c-14.9 35.7-46.2 87.7-93 131.1C433.5 443.2 368.8 480 288 480s-145.5-36.8-192.6-80.6C48.6 356 17.3 304 2.5 268.3c-3.3-7.9-3.3-16.7 0-24.6C17.3 208 48.6 156 95.4 112.6zM288 336c44.2 0 80-35.8 80-80s-35.8-80-80-80c-.7 0-1.3 0-2 0c1.3 5.1 2 10.5 2 16c0 35.3-28.7 64-64 64c-5.5 0-10.9-.7-16-2c0 .7 0 1.3 0 2c0 44.2 35.8 80 80 80zm0-208a128 128 0 1 1 0 256 128 128 0 1 1 0-256z"/></svg>
            <img :src="url.img" alt="" class="img-fluid">
        </figure>
    </div>

    <IndicatorsCarousel :items="reviews" class="mb-2"/>
    
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

#advertisement{
    padding-block: 10px;
    figure{
        position: relative;
        width: calc(100% / 4);
        padding-inline: 5px;
        &:first-child{
            padding-left: 0;
        }
        &:last-child{
            padding-right: 0;
        }
        &:hover{
            cursor: pointer;
            background-image: url(../../img/hover.png);
            background-size: contain;
        }
        &:hover img{
            display: none;
        }
        &:hover svg{
            display: block;
        }
        svg{
            fill: $white;
            background-color: $orange;
            border-radius: 50%;
            padding: 25px;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            display: none;
        }
    }
}

</style>
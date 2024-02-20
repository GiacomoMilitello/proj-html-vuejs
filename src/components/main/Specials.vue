<script>
export default {
  name: "Specials",
  components: {
},
  data() {
        return {
            specials: [
                {
                    price : '10',
                    name : 'combo piccolo',
                    description: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nostrum odio temporibus'
                },
                {
                    price : '20',
                    name : 'combo mezzo',
                    description: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nostrum odio temporibus'
                },
                {
                    price : '30',
                    name : 'combo grande',
                    description: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nostrum odio temporibus'
                },
            ],
        };
    }
};
</script>

<template>
    <div class="row">
        <figure class="col-6 d-flex align-items-center justify-content-center">
            <img src="../../img/h1-img-7n.png" alt="">
        </figure>
        <div class="col-6 d-flex justify-content-center align-items-center">
            <div class="w-50">
                <h3>SPECIALS*</h3>
                <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nostrum odio temporibus.</p>

                <ul class="mt-4">
                    <li v-for="(special, index) in specials" :key="index" class="row">
                        <span class="col-2 fw-bold">$ {{ special.price }}</span>
                        <h5 class="col-10 text-uppercase "> {{ special.name }}</h5>
                        <span class="col-2"></span>
                        <p class="col-10">{{ special.description }}</p>
                    </li>
                </ul>
            </div>
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

    figure{
        background-image: url(src/img/h1-img-4.jpg);
        @include bg-cover
    }
    .col-6{
        height: 700px;
        span{
            color: $orange;
            font-size: 140%;
            line-height: 33.6px;
        }
        h5{
            line-height: 33.6px;
        }
    }

</style>
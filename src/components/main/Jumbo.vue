<script>
export default {
  name: "Jumbo",
};
</script>

<template>
    
    <div id="jumbo" class="my-2">

<!-- BACKGROUNDS -->
        <div class="row small bottom">
            <div class="col-1"></div>
            <div class="col-10"></div>
            <div class="col-1"></div>
        </div>
        <div class="row big top">
            <div class="col-1"></div>
            <div class="col-10"></div>
            <div class="col-1"></div>
        </div>
        <div class="row small center">
            <div class="col-1"></div>
            <div class="col-10"></div>
            <div class="col-1"></div>
        </div>

<!-- TITLE -->
            <h2 class="">GO AHEAD AND BUILD YOUR OWN PIZZA <br>
            WE WON'T JUDGE!</h2>
    </div>

</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

    #jumbo{
        position: relative;
        h2{
            width: 20%;
            font-size: 350%;
            color: $white;
            position: absolute;
            left: 20%;
            top: 50%;
            transform: translateY(-50%);
            z-index: 1;
        }
        .small{
            height: 125px;
        }
        .big{
            height: 300px;
        }
        .col-1,
        .col-10{
            background-image: url(../../img/h3-background-img.jpg);
        }
        .center .col-1,
        .center .col-10{
            background-position: center;
        }
        .top .col-1,
        .top .col-10{
            background-position: top;
        }
        .bottom .col-1,
        .bottom .col-10{
            background-position: bottom;
        }
    }
    
</style>
<script>
export default {
  name: "IndicatorsCarousel",
  props: {
    items: {
        type: Array,
        required: true
    }
  },
  data() {
    return {
      activeIndex: 0
    };
  },
  methods: {
    next() {
      this.activeIndex++;
      if (this.activeIndex >= this.items.length) {
        this.activeIndex = 0;
      }
    },
    prev() {
      this.activeIndex--;
      if (this.activeIndex < 0) {
        this.activeIndex = this.items.length - 1;
      }
    }
  },
  mounted() {
    setInterval(() => {
      this.next();
    }, 5000);
  },
};
</script>

<template>
    <div id="carouselExampleRide" class="carousel slide carousel-fade" data-bs-ride="true">
      <div class="carousel-inner">
        <div class="carousel-item" v-for="(item, index) in items" :key="index" :class="{ active: index === activeIndex }">
          <div id="back" :style="{ backgroundImage: 'url(' + item.back + ')' }">
                <div id="front" class="w-25 mx-auto d-flex flex-column justify-content-center align-items-center ">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M0 216C0 149.7 53.7 96 120 96h8c17.7 0 32 14.3 32 32s-14.3 32-32 32h-8c-30.9 0-56 25.1-56 56v8h64c35.3 0 64 28.7 64 64v64c0 35.3-28.7 64-64 64H64c-35.3 0-64-28.7-64-64V320 288 216zm256 0c0-66.3 53.7-120 120-120h8c17.7 0 32 14.3 32 32s-14.3 32-32 32h-8c-30.9 0-56 25.1-56 56v8h64c35.3 0 64 28.7 64 64v64c0 35.3-28.7 64-64 64H320c-35.3 0-64-28.7-64-64V320 288 216z"/></svg>
                    <p class="text-uppercase fw-bold text-center mt-4">{{ item.review }}</p>
                    <p class="orange text-uppercase fw-bold">{{ item.magazine }}</p>
                    <div class="indicators d-flex gap-1">
                        <div class="indicator" v-for="(item, index) in items" :key="index" @click="activeIndex = index" :class="{ active: index === activeIndex }">
                        </div>
                    </div>
                </div>
          </div>
        </div>
      </div>
        <button class="carousel-control-prev" type="button" @click="prev">
            <div class="arrow arrow-prev" aria-hidden="true">
                <div class="prev"></div>
            </div>
            <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" @click="next">
            <div class="arrow arrow-next" aria-hidden="true">
                <div class="next"></div>
            </div>
            <span class="visually-hidden">Next</span>
        </button>
    </div>
  </template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;
@use "../styles/partials/mixins" as *;

#carouselExampleRide{
    height: 350px;
    svg{
        fill: $ochre;
        width: 80px;
        height: 80px 
    }
    .indicator {
        width: 10px;
        height: 10px;
        border-radius: 50%;
        margin: 5px;
        cursor: pointer;
        background-color: $light-ecru; // default color
        &.active {
            background-color: $ochre; // color when active
        }
    }
  #back,
  #front{
    height: 350px;
    @include bg-cover;
  }
  img{
    max-width: 280px
  }
  .carousel-control-prev{
    justify-content: start;
    opacity: 1;
  }
  .carousel-control-next{
    justify-content: end;
    opacity: 1;
  }
  .arrow{
    height: 60px;
    width: 25px;
    overflow: hidden;
    .prev,
    .next{
      height: 60px;
      width: 60px;
      background-color: $white;
      border-radius: 50%;
      padding: 10px;
      background-position: 10px center;
      background-repeat: no-repeat;
      background-size: 15%;
      // &:hover{
      //   background-color: $off-white;
      // }
    }
    .prev{
      background-image: url(../img/prev.png);
    }
    .next{
      background-image: url(../img/next.png);
    }
  }
  .arrow-prev{
    transform: rotate(180deg)
  }
}

</style>
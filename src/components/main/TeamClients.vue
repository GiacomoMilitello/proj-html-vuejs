<script>
export default {
  name: "TeamClients",
  components: {
},
  data() {
        return {
            workers: [
                {
                    img : 'src/img/h1-team-1a.jpg',
                    name : 'frank bailey',
                    job: 'kitchen porter'
                },
                {
                    img : 'src/img/h1-team-2a.jpg',
                    name : 'Sophia Johnson',
                    job: 'Waitress'
                },
                {
                    img : 'src/img/h1-team-4a.jpg',
                    name : 'James Williams',
                    job: 'Restaurant Manager'
                },
                {
                    img : 'src/img/h1-team-3a.jpg',
                    name : 'Emily Smith',
                    job: 'Pizza Chef'
                },
            ],
            clients: [
                { url : 'src/img/h1-clients-img-4.png' },
                { url : 'src/img/h1-clients-img-3.png' },
                { url : 'src/img/h1-clients-img-1.png' },
                { url : 'src/img/h1-clients-img-2.png' },
                { url : 'src/img/h1-clients-img-5.png' },
            ]
        };
    }
};
</script>

<template>

<!-- -- TEAM -- -->
    <div id="team" class="d-flex flex-wrap">
        <div id="card" v-for="(worker, index) in workers" :key="index" class="d-flex">
            <figure>
                <img class="img-fluid" :src="worker.img" alt="">
<!-- hover-div team -->
                <div class="hover-div d-flex align-items-center justify-content-center ">
                    <div class="d-flex flex-column justify-content-center align-items-center">
                        <h5 class="text-uppercase">{{ worker.name }}</h5>
                        <span class="text-capitalize">{{ worker.job }}</span>
                        <ul class="d-flex gap-2 mt-3">
                            <li>
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"/></svg></a>
                            </li>
                            <li>
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M64 32C28.7 32 0 60.7 0 96V416c0 35.3 28.7 64 64 64H384c35.3 0 64-28.7 64-64V96c0-35.3-28.7-64-64-64H64zm297.1 84L257.3 234.6 379.4 396H283.8L209 298.1 123.3 396H75.8l111-126.9L69.7 116h98l67.7 89.5L313.6 116h47.5zM323.3 367.6L153.4 142.9H125.1L296.9 367.6h26.3z"/></svg></a>
                            </li>
                            <li>
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M64 32C28.7 32 0 60.7 0 96V416c0 35.3 28.7 64 64 64h98.2V334.2H109.4V256h52.8V222.3c0-87.1 39.4-127.5 125-127.5c16.2 0 44.2 3.2 55.7 6.4V172c-6-.6-16.5-1-29.6-1c-42 0-58.2 15.9-58.2 57.2V256h83.6l-14.4 78.2H255V480H384c35.3 0 64-28.7 64-64V96c0-35.3-28.7-64-64-64H64z"/></svg></a>
                            </li>
                        </ul>
                    </div>
                </div>
            </figure>


        </div>
    </div>

<!-- -- CLIENTS -- -->
    <div id="clients" class="d-flex justify-content-center align-items-center p-5">
        <figure v-for="(client, index) in clients" :key="index">
            <img :src="client.url" alt="">
        </figure>
    </div>
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

#team {
    #card {
        position: relative;
        width: calc(100% / 4);
        cursor: pointer;
        figure{
            &:hover .hover-div{
                opacity: 1;
        }
        }
        .hover-div {
            position: absolute;
            top: 0;
            left: 0%;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity .3s ease;
            background-image: url(../../img/hover.png);
            background-size: contain;
            z-index: 1;

            & > div {
                background-color: $orange;
                width: 90%;
                height: 90%;

                span,
                h5 {
                    color: $white;
                }

                a {
                    svg {
                        fill: $white;
                        width: 20px;
                        height: 20px;
                    }

                    &:hover svg {
                        fill: $black;
                    }
                }
            }
        }
    }
}

#clients{
    background-color: $light-ecru;
    figure{
        &:hover{
            cursor: pointer;
        }
    }
}
</style>
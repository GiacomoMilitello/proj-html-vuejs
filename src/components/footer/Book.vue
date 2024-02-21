<script>
export default {
  name: "Book",
  data() {
    return {
      selectedPeople: '',
      selectedTime: '',
      selectedDate: '',
      bookPeople: '',
      bookTime: '',
      bookDate: '',
      showConfirmation: false
    };
  },
  methods: {
        selectPeople(people) {
            this.selectedPeople = people;
        },

        selectTime(time) {
            this.selectedTime = time;
        },
        bookTable() {
        if (this.selectedPeople && this.selectedTime && this.selectedDate) {

            this.bookPeople = this.selectedPeople;
            this.bookTime = this.selectedTime;
            this.bookDate = this.selectedDate;

            this.showConfirmation = true;

            this.selectedPeople = '';
            this.selectedTime = '';
            this.selectedDate = '';
        }
        }
    }
};
</script>

<template>
    <div id="book" class="p-5 mt-2">
        <div class="d-flex align-items-center justify-content-center">

<!-- input people -->
            <div class="width-one input-group my-5">
                <input id="people" type="text" class="form-control d-flex align-items-center " aria-label="Text input with dropdown button" placeholder="choose one option" v-model="selectedPeople">
                <button class="btn" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                    <svg height="25px" width="25px" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"><path d="M96 128a128 128 0 1 1 256 0A128 128 0 1 1 96 128zM0 482.3C0 383.8 79.8 304 178.3 304h91.4C368.2 304 448 383.8 448 482.3c0 16.4-13.3 29.7-29.7 29.7H29.7C13.3 512 0 498.7 0 482.3zM609.3 512H471.4c5.4-9.4 8.6-20.3 8.6-32v-8c0-60.7-27.1-115.2-69.8-151.8c2.4-.1 4.7-.2 7.1-.2h61.4C567.8 320 640 392.2 640 481.3c0 17-13.8 30.7-30.7 30.7zM432 256c-31 0-59-12.6-79.3-32.9C372.4 196.5 384 163.6 384 128c0-26.8-6.6-52.1-18.3-74.3C384.3 40.1 407.2 32 432 32c61.9 0 112 50.1 112 112s-50.1 112-112 112z"/></svg>
                </button>
                <ul class="dropdown-menu dropdown-menu-end">
                    <li class="dropdown-item" @click="selectPeople('1 Person')">1 Person</li>
                    <li class="dropdown-item" @click="selectPeople('2 People')">2 People</li>
                    <li class="dropdown-item" @click="selectPeople('3-4 People')">3-4 People</li>
                    <li class="dropdown-item" @click="selectPeople('5-10 People')">5-10 People</li>
                    <li class="dropdown-item" @click="selectPeople('11+ People')">11+ People</li>
                    
                </ul>
            </div>

            <h4 class="width-two white text-center my-5">FOR</h4>

<!-- input date -->
            <input class="width-one d-flex align-items-center" type="date" id="data" name="data" v-model="selectedDate">

            <h4 class="width-two white text-center my-5">AT</h4>
        
<!-- input hours -->
            <div class="width-one input-group">
                <input id="time" type="text" class="form-control d-flex align-items-center " aria-label="Text input with dropdown button" placeholder="choose one option" v-model="selectedTime">
                <button class="btn" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                    <svg height="25px" width="25px" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M464 256A208 208 0 1 1 48 256a208 208 0 1 1 416 0zM0 256a256 256 0 1 0 512 0A256 256 0 1 0 0 256zM232 120V256c0 8 4 15.5 10.7 20l96 64c11 7.4 25.9 4.4 33.3-6.7s4.4-25.9-6.7-33.3L280 243.2V120c0-13.3-10.7-24-24-24s-24 10.7-24 24z"/></svg>
                </button>
                <ul class="dropdown-menu dropdown-menu-end">
                    <li class="dropdown-item" @click="selectTime('7:00 pm')">7:00 pm</li>
                    <li class="dropdown-item" @click="selectTime('8:00 pm')">8:00 pm</li>
                    <li class="dropdown-item" @click="selectTime('9:00 pm')">9:00 pm</li>
                    <li class="dropdown-item" @click="selectTime('10:00 pm')">10:00 pm</li>
                </ul>
            </div>

            <h4 class="width-two none my-5">none</h4>

            <button class="btn-orange my-5" @click="bookTable">BOOK A TABLE</button>
        </div>
        <div v-if="showConfirmation">
            <h2 class="white text-center fw-bold">WE HAVE RECEIVED YOUR REQUEST</h2>
            <p class="white text-center fw-bold">
                TABLE FOR {{ bookPeople }} FOR {{ bookDate }} AT {{ bookTime }} <br>
                YOU WILL SOON RECEIVE A CONFIRMATION MESSAGE
            </p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

    #book{
        background-image: url(../../img/book.jpg);
        @include bg-cover;
        button{
            border: none;
        }
        .btn-orange{
            padding-inline: 100px;
        }
        .width-one{
            width: calc((80% / 4));
        }
        .width-two{
            width: calc(20% / 3);
        }
        .none{
            opacity: 0;
        }
        h4{
            margin-bottom: 0;
        }
        input{
            height: 43px;
            border: 2px solid $black;
            padding-inline: 20px;
        }
        .form-control, .btn{
            border-radius: 0;
            border: 2px solid $black;
        }
        .form-control{
            border-right: none;
        }
        .btn{
            border-left: none;
        }
        .btn{
            background-color: $white;
            &:hover{
                background-color: $off-white;
            }
        }
        svg{
            fill: $orange;
        }
        li{
            cursor: pointer;
        }
    }

</style>
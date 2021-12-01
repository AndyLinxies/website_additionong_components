<template>
  <div>
    <div class="justify-center globale mb-20">
      <p class="text-4xl font-extrabold mb-6">Our Pricing</p>
      <div class="flex justify-center">
        <p class="font-bold text-xl annuM">Anually</p>
        <!-- Rounded switch -->
        <label class="switch">
        <input type="checkbox" @click="active = !active" />
          <span class="slider round"></span>
        </label>
        <p class="font-bold text-xl annuM">Monthly</p>
      </div>
    </div>
    <!-- Cartes -->
    <div class="cartes xl:flex lg:block md:block sm:block w-30">
      <div
        class="max-w-xs mx-auto overflow-hidden bg-white rounded-lg shadow-lg dark:bg-gray-800 card_white pt-8"
      >
        <p>Basic</p>
        <p class="text-5xl font-black infos">
          ${{ active ? monBasic : annBasic }}
        </p>
        <hr v-if="active" />
        <!-- <p class="text-5xl font-black infos" v-if="!active" >${{annBasic}}</p><hr> -->
        <p class="mt-10 infos">500GB Storage</p>
        <hr />
        <p class="mt-10 infos">2 Users Allowed</p>
        <hr />
        <p class="mt-10 infos">Send up to 3 GB</p>
        <hr />
        <button class="mt-10 learn font-black">LEARN MORE</button>
      </div>
      <div
        class="max-w-xs mx-auto overflow-hidden bg-white rounded-lg shadow-lg dark:bg-gray-800 card text-white pt-8"
      >
        <p>Professional</p>
        <p class="text-5xl font-black mt-3 infos" v-if="active">
          ${{ monProf }}
        </p>
        <hr v-if="active" />
        <p class="text-5xl font-black infos" v-if="!active">${{ annProf }}</p>
        <hr />
        <p class="mt-10 infos">1 TB Storage</p>
        <hr />
        <p class="mt-10 infos">5 Users Allowed</p>
        <hr />
        <p class="mt-10 infos">Send up to 10 GB</p>
        <hr />
        <button class="mt-10 learn2 text-blue-600 font-black">
          LEARN MORE
        </button>
      </div>
      <div
        class="max-w-xs mx-auto overflow-hidden bg-white rounded-lg shadow-lg dark:bg-gray-800 card_white2 pt-8"
      >
        <p>Master</p>
        <p class="text-5xl font-black infos" v-if="active">${{ monMast }}</p>
        <hr v-if="active" />
        <p class="text-5xl font-black infos" v-if="!active">${{ annMast }}</p>
        <hr />
        <p class="mt-10 infos">2 TB Storage</p>
        <hr />
        <p class="mt-10 infos">10 Users Allowed</p>
        <hr />
        <p class="mt-10 infos">Send up to 20 GB</p>
        <hr />
        <button class="mt-10 learn font-black">LEARN MORE</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Pricings',
    data() {
    return {
      annBasic: 199.99,
      annProf: 249.99,
      annMast: 399.99,
      monBasic: 19.99,
      monProf: 24.99,
      monMast: 39.99,
      active: false
    };
  },
};
</script>

<style scoped>
.learn{
  background: linear-gradient(150deg, hsl(236, 72%, 90%) 0%, hsl(237, 63%, 64%) 50%);
  width: 60%;
  height: 5vh;
  border-radius: 10px;
  border: 1px solid white;
  color: beige;

}

.learn2{
  /* background: linear-gradient(150deg, hsl(236, 72%, 90%) 0%, hsl(237, 63%, 64%) 50%); */
  width: 60%;
  height: 5vh;
  border-radius: 10px;
  border: 1px solid hsl(236, 72%, 90%);
  background-color: honeydew;
}

.annuM {
  color: grey;
}

hr{
  width: 70%;
  margin-left: 15%;
}

.card_white{
  margin-top: 1%;
  height: 52vh;
  width: 60vw;
  margin-right: -250px;
}
.card_white2{
  margin-top: 1%;
  height: 52vh;
  width: 60vw;
  margin-left: -250px;
  z-index: -1;
}

.card{
  height: 57vh;
  width: 70vw;
  background: linear-gradient(150deg, hsl(236, 72%, 90%) 0%, hsl(237, 63%, 64%) 50%)
}

/* The switch - the box around the slider */
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
  margin-left: 2%;
  margin-right: 2%;
}

/* Hide default HTML checkbox */
.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

/* The slider */
.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
    background: linear-gradient(150deg, hsl(236, 72%, 90%) 0%, hsl(220, 63%, 64%) 50%);
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

input:checked + .slider {
  /* background-color:  */
    background: linear-gradient(150deg, hsl(236, 72%, 90%) 0%, hsl(237, 63%, 64%) 50%)

}

input:focus + .slider {
  box-shadow: 0 0 1px #797fe1;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
</style>

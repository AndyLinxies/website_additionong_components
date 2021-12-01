<template>
  <div id="app">
    <!--First section-->
    <div>
      <!--top card-->
      <ReproCard
        :title="titleTop"
        :paragraphe="paragrapheTop"
        :name="nameTop"
        :date="dateTop"
        :image="imageTop"
      />
      <!--top card-->
      <ReproCard
        :title="titleBottom"
        :paragraphe="paragrapheBottom"
        :name="nameBottom"
        :date="dateBottom"
        :image="imageBottom"
      />
    </div>

    <!--Second section Pricings-->
    <div class="mt-40">
      <Pricings />
    </div>

    <!--Third section Pricings-->
    <div>
      <Form />
    </div>

    <!--Last section Slider Testimonials-->
    <div>
      <Slider />
    </div>
  </div>
</template>

<script>
import ReproCard from "./components/ReproCard.vue";
import Pricings from "./components/Pricings.vue";
import Form from "./components/Form.vue";
import Slider from "./components/Slider";

export default {
  name: "App",
  components: {
    ReproCard,
    Pricings,
    Form,
    Slider,
  },
  data() {
    return {
      titleTop:
        "Shift the overall look and feel by adding these wonderful touches to furniture in your home",
      paragrapheTop:
        "Ever been in a room and felt like som Perhaps it felt slightly bare and unin simple tips to help you make any roo!",
      nameTop: "Michelle Appleton",
      dateTop: "28 Jun 2020",
      imageTop: "../../src/assets/imgCard/avatar-michelle.jpg",
      // imageTop: './assets/imgCard/avatar-michelle.jpg',

      titleBottom:
        "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Consequatur quidem nesciunt ",
      paragrapheBottom:
        "cupiditate natus harum accusamus molestiae sequi quis ullam neque.",
      nameBottom: "Nick Cameron",
      dateBottom: "1st Dec 2021 ",
      imageBottom:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcThjr6EmzLIS6xK8noIpfAgFZcr5g1lBnpNdw&usqp=CAU",
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

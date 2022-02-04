<template>
  <div id="app">
    <section class="container">
      <header>
        <AddForm @addNewFruit="addNewFruit()" />
        <Nav />
      </header>
      <main>
        <div v-for="(fruit, index) in fruits" :key="index">
          <FruitCard :fruit="fruit" @deleteFruit="deleteFruit(index)" />
        </div>
      </main>
    </section>
  </div>
</template>

<script>
import Nav from "@/components/Nav.vue";
import AddForm from "@/components/AddForm.vue";
import FruitCard from "@/components/FruitCard.vue";

export default {
  name: "App",
  components: {
    Nav,
    AddForm,
    FruitCard,
  },
  // props: ["newName", "newQty", "newPrice"],
  data() {
    return {
      fruits: [
        {
          thumb: "strawberry.png",
          name: "Fragole deliziose",
          qty: 256,
          price: 2.35,
        },
        {
          thumb: "lemon.png",
          name: "Limone succoso",
          qty: 354,
          price: 1.4,
        },
        {
          thumb: "oranges.png",
          name: "Arancia rossa",
          qty: 0,
          price: 3.75,
        },
        {
          thumb: "pineapple.png",
          name: "Ananas del Brasile",
          qty: 123,
          price: 10.6,
        },
        {
          thumb: "cherries.png",
          name: "Ciliegia Ferrovia",
          qty: 0,
          price: 1.23,
        },
      ],
    };
  },
  methods: {
    deleteFruit: function(index) {
      this.fruits.splice(index, 1);
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/app.scss";
</style>

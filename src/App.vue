<template>
  <div id="app">
    <section class="container">
      <header>
        <!-- head-title + form button -->
        <div>
          <div class="row head-title">
            <div class="col-6">
              <h1><a href="#">My Fruit Shop</a></h1>
            </div>
            <div class="col-6 d-flex justify-content-end align-items-center">
              <div
                @click="formVisible()"
                class="tag
          d-inline-block
          custom-btn
          btnToggle pointer"
                :class="isVisible === false ? 'add' : 'close-btn'"
              >
                {{ isVisible === false ? "Aggiungi +" : "Chiudi X" }}
              </div>
            </div>
          </div>

          <!-- form -->
          <div
            class="row
      align-items-center
      justify-content-center
      m-0
      mb-3"
            :class="isVisible === false ? 'd-none' : ''"
          >
            <!-- name -->
            <div class="col-1"></div>
            <div class="col-4">
              <input
                type="text"
                class="input"
                id="input-name"
                placeholder="Descrizione prodotto"
                v-model.trim="newName"
              />
            </div>

            <!-- quantity -->
            <div class="col-2">
              <input
                type="number"
                class="input"
                id="input-qty"
                placeholder="Qta"
                v-model.trim="newQty"
              />
            </div>

            <!-- price -->
            <div class="col-2">
              <input
                type="number"
                step=".01"
                name="price"
                class="input"
                id="input-price"
                placeholder="Prezzo"
                v-model.trim="newPrice"
              />
            </div>
            <div class="col-1"></div>

            <!-- submit button -->
            <div class="col-1">
              <button
                type="submit"
                class="tag true custom-btn "
                @click="addNewFruit()"
              >
                Conferma
              </button>
            </div>
            <div class="mb-3 mt-4 line"></div>
          </div>
        </div>

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
import FruitCard from "@/components/FruitCard.vue";

export default {
  name: "App",
  components: {
    Nav,
    FruitCard,
  },
  props: ["newName", "newQty", "newPrice"],
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
      isVisible: false,
    };
  },
  methods: {
    // delete fruit
    deleteFruit(index) {
      this.fruits.splice(index, 1);
    },

    // add new fruit
    addNewFruit() {
      const newFruit = {
        thumb: "fruits.png",
        name: this.newName,
        qty: ~~this.newQty,
        price: +this.newPrice,
      };
      if (newFruit.name != "" && newFruit.qty > 0 && newFruit.price > 0) {
        this.fruits.push(newFruit);
      }
      // this.newFruit = "";
      this.newName = "";
      this.newQty = NaN;
      this.newPrice = NaN;
    },

    // form visibility
    formVisible() {
      return (this.isVisible = !this.isVisible);
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/app.scss";
</style>

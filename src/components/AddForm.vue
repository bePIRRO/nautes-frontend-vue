<template>
  <div>
    <div class="row head-title">
      <div class="col-6">
        <h1>My Fruit Shop</h1>
      </div>
      <div class="col-6 d-flex justify-content-end align-items-center pointer">
        <div
          @click="formVisible()"
          class="tag
          d-inline-block
          custom-btn
          btnToggle"
          :class="isVisible === false ? 'add' : 'close-btn'"
        >
          {{ isVisible === false ? "Aggiungi +" : "Chiudi X" }}
        </div>
      </div>
    </div>

    <div
      class="row
      align-items-center
      justify-content-center
      m-0
      mb-3"
      :class="isVisible === false ? 'd-none' : ''"
    >
      <div class="col-1"></div>
      <div class="col-4">
        <input
          type="text"
          class="input"
          placeholder="Descrizione prodotto"
          v-model.trim="newName"
        />
      </div>
      <div class="col-2">
        <input
          type="text"
          id="qty"
          class="input"
          placeholder="Qta"
          v-model.trim="newQty"
        />
      </div>
      <div class="col-2">
        <input
          type="text"
          name="price"
          class="input"
          placeholder="Prezzo"
          v-model.trim="newPrice"
        />
      </div>
      <div class="col-1"></div>
      <div class="col-1">
        <button
          type="submit"
          class="tag true pointer custom-btn"
          @click="$emit(addNewFruit())"
        >
          Conferma
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AddForm",
  components: {},
  props: ["newName", "newQty", "newPrice"],
  data() {
    return {
      isVisible: false,
    };
  },
  methods: {
    // form visibility
    formVisible() {
      return (this.isVisible = !this.isVisible);
    },

    // add new fruit
    addNewFruit() {
      const newFruit = {
        thumb: "",
        name: this.newName,
        qty: this.newQty,
        price: this.newPrice,
      };
      this.fruits.push(newFruit);
      console.log("aggiunto frutto" + newFruit);

      this.newFruit = {
        thumb: "",
        name: "",
        qty: "",
        price: "",
      };
    },
  },
};
</script>

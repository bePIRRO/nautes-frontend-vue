<template>
  <div>
    <div class="row head-title">
      <div class="col-6">
        <h1>My Fruit Shop</h1>
      </div>
      <div class="col-6 d-flex justify-content-end align-items-center pointer">
        <div
          onClick=""
          class="tag
          d-inline-block
          custom-btn
          btnToggle"
        >
          btntext
        </div>
      </div>
    </div>

    <div
      class="row
      align-items-center
      justify-content-center
      m-0
      mb-3"
    >
      <div class="col-1"></div>
      <div class="col-4">
        <input
          type="text"
          name="name"
          id="name"
          class="input"
          onChange=""
          value=""
          placeholder="Descrizione prodotto"
        />
      </div>
      <div class="col-2">
        <input
          type="text"
          name="qty"
          id="qty"
          class="input"
          onChange=""
          value=""
          placeholder="Qta"
        />
      </div>
      <div class="col-2">
        <input
          type="text"
          name="price"
          id="price"
          class="input"
          onChange=""
          value=""
          placeholder="Prezzo"
        />
      </div>
      <div class="col-1"></div>
      <div class="col-1">
        <button type="submit" class="tag true pointer custom-btn" onClick="">
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
  props: {},
};
</script>

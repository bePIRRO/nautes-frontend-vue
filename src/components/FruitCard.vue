<template>
  <div class="d-flex fruit align-items-center justify-content-center mb-3">
    <div class="col-1">
      <figure class="fruit-img d-flex justify-content-center">
        <img class="img-fluid" src="" alt="" />
      </figure>
    </div>
    <div class="col-5 fruit-name">
      <h6>{{ fruit.name }}</h6>
    </div>
    <div class="col-1 fruit-qty">{{ fruit.qty }} pz</div>
    <div class="col-1 fruit-frice ps-3">{{ fruit.price.toFixed(2) }} €</div>
    <div class="col-2 fruit-avaibility d-flex justify-content-center">
      <div class="tag">{{ fruit.status }}</div>
    </div>
    <div class="col-1 fruit-delete text-center">
      <figure>
        <img src="" alt="delete" onClick="" />
      </figure>
    </div>
  </div>
</template>

<script>
export default {
  name: "FruitCard",
  components: {},
  props: ["fruit"],
  methods: {
    isAvaible: "true",
    status: "Disponibile",
    // if (qty === 0) {
    //   isAvaible = "false";
    //   status = "Esaurito";
    // }
    // // get img url
    // function getImg() {
    //   return require(`../images/${thumb}`);
    // }
    // // remove fruit
    // function removeFruit() {
    //   console.log("eliminato " + name);
    //   return fruits.splice(fruit, 1);
    // }
  },
};
</script>

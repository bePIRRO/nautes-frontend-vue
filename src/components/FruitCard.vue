<template>
  <div class="d-flex fruit align-items-center justify-content-center mb-3">
    <div class="col-1">
      <figure class="fruit-img d-flex justify-content-center">
        <img class="img-fluid" :src="getImg(fruit.thumb)" :alt="fruit.name" />
      </figure>
    </div>
    <div class="col-5 fruit-name">
      <h6>{{ fruit.name }}</h6>
    </div>
    <div class="col-1 fruit-qty">{{ fruit.qty }} pz</div>
    <div class="col-1 fruit-frice ps-3">{{ fruit.price.toFixed(2) }} €</div>
    <div class="col-2 fruit-avaibility d-flex justify-content-center">
      <div class="tag" :class="fruit.qty > 0 ? 'true' : 'false'">
        {{ fruit.qty > 0 ? "Disponibile" : "Esaurito" }}
      </div>
    </div>
    <div class="col-1 fruit-delete text-center">
      <figure>
        <img
          src="../assets/images/icons/cross.png"
          alt="delete"
          class="pointer"
          @click="$emit('deleteFruit')"
        />
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
    // get img url
    getImg() {
      return require(`@/assets/images/${this.fruit.thumb}`);
    },
  },
};
</script>

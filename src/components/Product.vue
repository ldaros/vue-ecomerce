<template>
  <div class="col-6 col-lg-3 col-md-4 mb-2">
    <div class="card p-2">
      <button
        id="add-to-cart"
        class="btn btn-primary align-self-end"
        @click="sendItem(product)"
      >
        +
      </button>

      <div class="big align-self-center">{{ product.image }}</div>

      <div class="card-body">
        <div class="row">
          <h4 class="col fs-5 card-title">{{ product.name }}</h4>
          <span class="col text-end">{{ product.weight }}Kg</span>
        </div>

        <div class="row card-text">
          <span class="col fw-bold fs-5 align-self-end" id="prod-price">
            ${{ product.price }}
          </span>
          <span class="col text-end align-self-end small">
            {{ product.stock }} units left</span
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "product",
  props: { product: Object },
  methods: {
    sendItem(product) {
      this.$emit("onAdd", product);
    },
  },
};
</script>

<style scoped>
.big {
  font-size: 8em;
}

.small {
  font-size: 0.8em;
}

@media screen and (max-width: 768px) {
  .big {
    font-size: 5em;
  }
}
</style>

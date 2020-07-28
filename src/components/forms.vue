<template>
  <div class="pt-2">
    <brand :brands="brands" :active="value.brand" @selected="selectActiveBrand" />
    <model :models="models" :active="value.model" @selected="selectActiveModel" />
    <color :colors="colors" :active="value.color" @selected="selectActiveColor" />
  </div>
</template>

<script>
import brand from "./forms/brand";
import model from "./forms/model";
import color from "./forms/color";

export default {
  props: {
    value: {
      type: Object,
      default: () => ({}),
    },
  },
  components: {
    brand,
    model,
    color,
  },
  data() {
    return {
      brands: [
        { id: 1, name: "Littmann", cost: 150 },
        { id: 2, name: "Spirit Medical", cost: 130 },
        { id: 3, name: "NaturFarm", cost: 95 },
        { id: 4, name: "Luxamed", cost: 75 },
      ],
      models: [
        { id: 1, name: "Intern", cost: 40 },
        { id: 2, name: "Cardio", cost: 60 },
        { id: 3, name: "Pediatric", cost: 30 },
        { id: 4, name: "Anesthesia", cost: 25 },
      ],
      colors: [
        { id: 1, name: "Summer Sun", color: "is-warning", img: "yellow.jpeg", hex: "#F3C947" },
        { id: 2, name: "Neon Pink", color: "is-danger", img: "pink.jpg", hex: "#F61974" },
        { id: 3, name: "Blueberry Blue", color: "is-link", img: "blue.jpg", hex: "#326CB5" },
        { id: 4, name: "Deep Black", color: "is-black", img: "black.jpg", hex: "#1D2023" },
        { id: 5, name: "Cactus Green", color: "is-success", img: "green.jpg", hex: "#356865" },
      ],
    };
  },
  methods: {
    selectActiveBrand(brand) {
      this.$emit('input', { ...this.value, brand })
    },
    selectActiveModel(model) {
      this.$emit('input', { ...this.value, model })
    },
    selectActiveColor(color) {
      this.$emit('input', { ...this.value, color })
    },
  },
};
</script>
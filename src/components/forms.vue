<template>
  <div class="pt-2">
    <brand :brands="brands" :active="value.brand" @selected="selectActiveBrand" />
    <model :models="models" :active="value.model" @selected="selectActiveModel" />
    <color :colors="colors" :active="value.color" @selected="selectActiveColor" />
    <personalization/>
  </div>
</template>

<script>
import brand from "./forms/brand";
import model from "./forms/model";
import color from "./forms/color";
import personalization from './forms/personalization'

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
    personalization
  },
  data() {
    return {
      brands: [
        { id: 1, name: "Littmann", cost: 160 },
        { id: 2, name: "Spirit Medical", cost: 140 },
        { id: 3, name: "NaturFarm", cost: 105 },
        { id: 4, name: "Luxamed", cost: 105 },
      ],
      models: [
        { id: 1, name: "Intern", cost: 60 },
        { id: 2, name: "Cardio", cost: 90 },
        { id: 3, name: "Pediatric", cost: 40 },
        { id: 4, name: "Anesthesia", cost: 45 },
      ],
      colors: [
        { id: 1, name: "Yellow", color: "is-warning", img: "yellow.png", hex: "#F3C947" },
        { id: 2, name: "Pink", color: "is-danger", img: "pink.png", hex: "#F61974" },
        { id: 3, name: "Blue", color: "is-link", img: "blue.png", hex: "#326CB5" },
        { id: 4, name: "Black", color: "is-black", img: "black.png", hex: "#1D2023" },
        { id: 5, name: "Green", color: "is-success", img: "green.png", hex: "#356865" },
        { id: 6, name: "Red", color: "is-danger", img: "red.png", hex: "#D6231E" },
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